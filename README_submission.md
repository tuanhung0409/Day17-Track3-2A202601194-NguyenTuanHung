# Báo Cáo Nghiệm Thu Lab 17 - Multi-Memory Agent

## 1. Ba Câu Hỏi Bắt Buộc

### Câu 1: Tầng nhớ quan trọng nhất trong bộ test
**Long-Term Memory** là tầng quan trọng nhất (chiếm 4/11 case practice: **E02, E03, E08, E09** và 4 case Golden: **G03-G06**). Nó giải quyết bài toán cốt lõi: lưu trữ và truy xuất các thuộc tính bền vững (user preferences, task open-loops, tech stack) xuyên suốt nhiều session. Điển hình: **E08** (trích xuất stack `BLUEBIRD-42` $\rightarrow$ `TypeScript/NestJS`) và **E09** (cô lập profile `Lan` khỏi `Minh`).

### Câu 2: Trade-off Zep Context Block vs Redis/Qdrant
- **Zep Context Block**: Tự động hóa trích xuất Knowledge Graph, xử lý mâu thuẫn thời gian (temporal invalidation) và tổng hợp facts ngắn gọn nạp vào prompt. Đổi lại: phụ thuộc Cloud API, latency cao hơn (~1.2s) và tốn credit.
- **Redis/Qdrant**: Truy vấn cực nhanh (<10ms), on-premise an toàn, chi phí thấp. Đổi lại: lập trình viên phải tự code toàn bộ pipeline entity extraction, decay và conflict resolution.

### Câu 3: Guardrail chống Memory Poisoning (Đầu độc bộ nhớ)
1. **Consent & Whitelist**: Kiểm tra opt-in và loại dữ liệu cho phép (`can_write_type`) trước khi ghi.
2. **Provenance & Verification**: Lưu vết nguồn gốc (source ID, timestamp), kiểm tra mâu thuẫn trước khi cập nhật fact.
3. **Heartbeat Boundary**: Quá trình bảo trì nền chỉ được dọn rác/khử trùng lặp; không tự ý chèn chỉ thị hay quyền hạn mới vào durable memory.

---

## 2. Phân Tích So Sánh (Comparison Analysis)

- **Câu 1 (Hit rate thấp nhất baseline)**: Tầng `long_term`, `episodic`, `semantic` ở baseline no-memory đều đạt **0% hit rate** do không có cơ chế lưu trữ liên phiên hay tra cứu tri thức miền.
- **Câu 2 (Case nhiều token nhất)**: **E08** (1424 tokens) và **E03** (1413 tokens) do Zep Context Block nạp toàn bộ profile tóm tắt của user.
- **Câu 3 (Case mixed E07)**: Kết hợp **Long-Term** (preference `Python` của Minh) và **Semantic** (chính sách `Idempotency-Key` từ `knowledge.jsonl`).
- **Câu 4 (Token reduction vs Hit rate)**: No-memory đạt token reduction cao (81.8%) chỉ vì nó không truy xuất gì; giảm token nhưng mất hoàn toàn độ chính xác (hit rate chỉ 18.2%).
