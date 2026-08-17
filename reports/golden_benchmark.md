# Lab 17 Golden Set Report

- Implementation: `student`
- Kind: `golden`
- Cases: **20**
- Passed: **20/20**
- Evidence hit rate: **100.0%**
- Average retrieval latency: **1250.4 ms**
- Average token reduction vs full source context: **8.1%**
- Golden bonus: **10/10** (100% required)

| Case | Layer | Pass | Latency ms | Retrieved tokens | Token reduction | Missing / Error |
| --- | --- | --- | ---: | ---: | ---: | --- |
| G01 | short_term | PASS | 0.2 | 227 | 0.0% |  |
| G02 | short_term | PASS | 0.0 | 133 | 0.0% |  |
| G06 | long_term | PASS | 1621.9 | 781 | 0.0% |  |
| G09 | semantic | PASS | 443.3 | 255 | 44.4% |  |
| G10 | semantic | PASS | 237.3 | 165 | 64.0% |  |
| G14 | mixed | PASS | 1854.9 | 502 | 0.0% |  |
| G03 | long_term | PASS | 1515.3 | 1408 | 0.0% |  |
| G04 | long_term | PASS | 1450.1 | 1438 | 0.0% |  |
| G07 | episodic | PASS | 250.5 | 482 | 0.0% |  |
| G08 | episodic | PASS | 245.0 | 478 | 0.0% |  |
| G11 | mixed | PASS | 1828.0 | 509 | 9.9% |  |
| G13 | mixed | PASS | 705.1 | 500 | 11.5% |  |
| G15 | mixed | PASS | 2185.9 | 831 | 0.0% |  |
| G16 | mixed | PASS | 3452.9 | 581 | 0.0% |  |
| G17 | mixed | PASS | 2926.5 | 581 | 0.0% |  |
| G18 | mixed | PASS | 474.8 | 500 | 11.5% |  |
| G19 | mixed | PASS | 1503.7 | 581 | 0.0% |  |
| G05 | long_term | PASS | 1267.5 | 1422 | 0.0% |  |
| G12 | mixed | PASS | 1461.1 | 502 | 20.6% |  |
| G20 | mixed | PASS | 1584.0 | 683 | 0.0% |  |

## Evidence excerpts

### G01 - short_term

`<SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. | assistant: Noted staging constraint. | user: Filler A about button padding. | assistant: Filler A. | user: Filler B about color tokens. | assistant: Filler B. | user: Filler C about copy tone. | assistant: Filler C. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. - user: Constraint HOLD-BETA-STAGING: writes go to staging DB only. - assistant: Noted staging constraint. </DURA`

### G02 - short_term

`<RECENT_TURNS> user: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. assistant: Da hieu: demo ca nhan ORCHID-27, uu tien Python, tranh Java, vi du ngan. user: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. assistant: Toi se uu tien timeline khi giai thich coroutine va Task. user: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-REPORT-1600. </RECENT_TURNS>`

### G06 - long_term

`<USER_SUMMARY> The user's project is LOTUS-88.  The user prioritizes Java and Spring Boot for backend examples and does not use Python in the backend. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho backend exampl`

### G09 - semantic

`EPISODE: {"id":"kb-payment-retry","entity":"Payment API Retry Policy","summary":"For POST /payments, every retryable request MUST send the same Idempotency-Key. Retry only HTTP 429 or transient 5xx errors, use exponential-backoff, and stop after max-3-retries. Marker: PAYMENT-RULE-3.","source":"internal-api-guideline-v3","updated_at":"2026-08-10T00:00:00Z"} EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} EPISODE: {"id":"`

### G10 - semantic

`EPISODE: {"id":"kb-memory-privacy","entity":"Agent Memory Privacy Rule","summary":"Do not persist personal data without explicit opt-in. A deletion request must remove user-scoped memory and be verified across every store. Marker: DELETE-VERIFY-ALL.","source":"memory-governance-policy","updated_at":"2026-08-12T00:00:00Z"} EPISODE: {"id":"kb-context-budget","entity":"Memory Context Budget","summary":"Reserve bounded context for memory. This lab uses short-term 10 percent, long-term 4 percent, episodic 3 percent, semantic 3 percent; trim lower-priority memory first. Marker: BUDGET-10-4-3-3.","source":"lab-design-note","updated_at":"2026-08-13T00:00:00Z"}`

### G14 - mixed

`<LONG_TERM> <USER_SUMMARY> The user's project is LOTUS-88.  The user prioritizes Java and Spring Boot for backend examples and does not use Python in the backend. </USER_SUMMARY>  <EPISODES> Episodes are source message or document excerpts shown in selection order.   - Created At: 2026-08-01 11:00:00     Source: message     Content: [user] {   "user_id": "lan-lab17",   "first_name": "Lan",   "last_name": "Tran",   "user_alias": "Lan Tran" }: Toi la Lan. Du an cua toi la LOTUS-88. Toi uu tien Java va Spring Boot, va khong dung Python trong vi du backend.   - Created At: 2026-08-01 11:00:20     Source: message     Content: Lab Assistant (assistant): Da hieu: LOTUS-88, Java + Spring Boot cho ba`

### G03 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometimes confuses c`

### G04 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometimes confuses c`

### G07 - episodic

`EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Minh sap viet script ca nhan de tai hien su co latency, muon code dung ngon ngu minh thich khi lam mot minh, dong thoi bam sat playbook incident cua lab chu dung vo tang timeo EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua EPISODE: Da ghi nhan trajectory: increase timeout khong hieu qua; Clie`

### G08 - episodic

`EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Minh sap viet script ca nhan de tai hien su co latency, muon code dung ngon ngu minh thich khi lam mot minh, dong thoi bam sat playbook incident cua lab chu dung vo tang timeo EPISODE: Toi dang hoc async/await va hay nham coroutine voi Task. Neu sau nay gap chu de nay, hay giai thich bang timeline. EPISODE: TODO: hoan thanh benchmark report truoc thu Sau luc 16:00. Day la open loop LAB-`

### G11 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometime`

### G13 - mixed

`<EPISODIC> EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Hom nay toi debug async HTTP. Toi da thu tang timeout len 60s nhung van fail. EPISODE: Chuan bi demo ca nhan: ten/ma project rieng cua Minh la gi, va lan async HTTP truoc minh reuse client nhu the nao (kem ma su co)? Khong can policy domain chung, chi memory cua EPISODE: Cong ty yeu cau chinh context window cho agent tren dung backend du an cong ty. Minh can biet stack bat buoc cua BLUEBIRD va ty le budget bon tang nho trong lab de cau hinh ch EPISODE: Mai hop mentor, toi nay minh muon don open-loop. L`

### G15 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometime`

### G16 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometime`

### G17 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometime`

### G18 - mixed

`<EPISODIC> EPISODE: Cach hieu qua la reuse aiohttp ClientSession va dat concurrency=20. Reflection: loi chinh la connection churn, khong phai timeout threshold. Ma su co ASYNC-FIX-20. EPISODE: Toi nay minh viet tool ca nhan de tai hien su co HTTP roi sua dung playbook. Can ba manh: ngon ngu minh thich khi lam mot minh, ma su co async lan truoc, va buoc playbook truo EPISODE: Minh con mot open-loop phai nop truoc deadline, dong thoi muon ghi chu retry payment dung so lan toi da theo policy. Nac lai ma task/deadline con dang do, va gioi han retry ch EPISODE: Ten du an ca nhan cua toi la ORCHID-27. Toi thich Python va khong thich Java. Khi giai thich code, hay dung vi du ngan. EPISODE: Hay kiem`

### G19 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometime`

### G05 - long_term

`<USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometimes confuses c`

### G12 - mixed

`<LONG_TERM> <USER_SUMMARY> Minh's personal project is named ORCHID-27, for which he prefers Python. For the company project BLUEBIRD-42, the backend must use TypeScript with NestJS; Python is not to be used for this project. He needs to complete a benchmark report for open loop LAB-REPORT-1600 before Friday at 4:00 PM. Minh is also debugging async HTTP and found that reusing the aiohttp ClientSession and setting concurrency to 20 resolved connection churn.  Minh prefers Python for personal projects like ORCHID-27 but requires TypeScript with NestJS for the company project BLUEBIRD-42. He dislikes Java. When explaining code, he prefers short examples. Minh is learning async/await and sometime`

### G20 - mixed

`<SHORT_TERM> <SESSION_SUMMARY> user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. | assistant: Noted standup constraint. | user: Filler about dashboard widgets. | assistant: Filler. | user: Filler about CSS variables. | assistant: Filler. | user: Filler about copy review. | assistant: Filler. </SESSION_SUMMARY> <DURABLE_NOTES> - user: Constraint HOLD-ALPHA-0900: standup is 09:00 sharp and must not be forgotten. - assistant: Noted standup constraint. </DURABLE_NOTES> <RECENT_TURNS> user: Filler about empty charts. assistant: Filler. user: Filler about telemetry. assistant: Filler. user: Filler about a11y labels. assistant: Filler. </RECENT_TURNS> </SHORT_TERM>`
