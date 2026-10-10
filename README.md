# 💰 Dashboard Personal Planning (Personal Finance Dashboard)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![CI](https://github.com/Software-Engineering-Concepts-2026/se-sec1-team-07/actions/workflows/ci.yml/badge.svg)](https://github.com/Software-Engineering-Concepts-2026/se-sec1-team-07/actions/workflows/ci.yml)
[![JavaScript tests](https://github.com/Software-Engineering-Concepts-2026/se-sec1-team-07/actions/workflows/test.yml/badge.svg)](https://github.com/Software-Engineering-Concepts-2026/se-sec1-team-07/actions/workflows/test.yml)

> **Dashboard Personal Planning** คือเว็บแอปพลิเคชันบริหารจัดการการเงินส่วนบุคคลแบบครบวงจร ช่วยติดตามรายรับ-รายจ่าย วางแผนเป้าหมายการออมเงิน ควบคุมงบประมาณประจำเดือน และแสดงผลสรุปทางการเงินผ่าน Interactive Dashboard ในแพลตฟอร์มเดียว

---

## 👥 ทีมผู้พัฒนา (Team Members - `se-sec1-team-07`)

* **ขวัญชีวา คำแดง** — GitHub: [@67024728](https://github.com/67024728)
* **รัตน์ติญาภรณ์ แหลมจัด** — GitHub: [@BEAMMMMMMMMM1234](https://github.com/BEAMMMMMMMMM1234)
* **พณิชพล สุวรรณหล้า** — GitHub: [@Mokub112](https://github.com/Mokub112)
* **วีรยา เกี๋ยงคำ** — GitHub: [@67021264Wirayakiangkham](https://github.com/67021264Wirayakiangkham) *(Testing, DevOps & Documentation Specialist)*

---

## ✨ ฟีเจอร์ของระบบ (Features)

ต้นแบบ Frontend อยู่ในโฟลเดอร์ [`frontend/`](./frontend/) มี 6 หน้า:

| หน้า | สิ่งที่ทำได้ | ไฟล์ |
| --- | --- | --- |
| **เข้าสู่ระบบ / สมัคร / ลืมรหัสผ่าน** | Login, สมัครสมาชิก, ตั้งรหัสผ่านใหม่ | [`index.html`](./frontend/index.html) |
| **Dashboard** | การ์ดสรุป 4 ช่อง (รายรับ, รายจ่าย, เงินคงเหลือ + อัตราออม, ออมสะสม), กราฟแท่งรายรับ vs รายจ่าย 6 เดือน, Donut สัดส่วนรายจ่ายตามหมวด, รายการล่าสุด | [`pages/dashboard.html`](./frontend/pages/dashboard.html) |
| **รายรับ-รายจ่าย** | เพิ่มรายการพร้อมหมวดหมู่และวันที่, ดูประวัติรายการ | [`pages/transactions.html`](./frontend/pages/transactions.html) |
| **เป้าหมาย** | ตั้งเป้าหมายการออม, ฝากเงินเพิ่ม, ดูความคืบหน้าและจำนวนวันที่เหลือ | [`pages/goals.html`](./frontend/pages/goals.html) |
| **งบประมาณ** | ตั้งงบรายหมวด เทียบกับยอดที่ใช้จริงพร้อมกราฟ | [`pages/budget.html`](./frontend/pages/budget.html) |
| **บัญชีส่วนตัว** | จัดการข้อมูลโปรไฟล์ | [`pages/profile.html`](./frontend/pages/profile.html) |

> **สถานะปัจจุบัน:** Frontend เป็นต้นแบบที่เก็บข้อมูลใน `localStorage` ของเบราว์เซอร์ (ยังไม่มี backend จริง) ส่วน [`services/stats-service`](./services/stats-service/) เป็น Flask service เริ่มต้นสำหรับ health check

### 🎁 จุดที่ใส่ใจประสบการณ์ผู้ใช้ (Delight Users)

* **ไม่ปล่อยหน้าว่างเปล่า:** เมื่อยังไม่มีข้อมูลจะแสดง Empty State พร้อมปุ่มชวนเริ่มต้น เช่น "เพิ่มรายการ" และ "ตั้งเป้าหมายใหม่"
* **เป้าหมายคำนวณให้เอง:** แสดงจำนวนวันที่เหลือ และแนะนำยอดที่ควรออมต่อเดือนโดยอัตโนมัติ
* **เห็นความคืบหน้าทันที:** Progress Bar ในเป้าหมายและงบประมาณ พร้อมสีและไอคอนอีโมจิประจำหมวดหมู่
* **ดูย้อนหลังได้:** ปุ่มเลื่อนเดือนก่อนหน้า/ถัดไป และตัวเลขเปรียบเทียบกับเดือนที่แล้ว
* **ใช้งานได้ทันที:** มีบัญชีทดลองให้ลอง ไม่ต้องสมัครก่อน

---

## 🚀 วิธีการติดตั้งและรันโปรเจกต์ (Quick Setup)

```bash
# 1. Clone repository
git clone https://github.com/Software-Engineering-Concepts-2026/se-sec1-team-07.git
cd se-sec1-team-07
```

### เปิดดูหน้าเว็บ (Frontend)

เปิดไฟล์ [`frontend/index.html`](./frontend/index.html) ในเบราว์เซอร์ได้เลย ไม่ต้องมี server

* บัญชีทดลอง: `demo@dpp.com` / `demo1234`

### รันชุดทดสอบ JavaScript (Vitest + fast-check)

```bash
npm ci
npm test
npm run test:coverage
```

### รันชุดทดสอบ Python (stats-service)

```bash
pip install -r services/stats-service/requirements.txt
pytest services/stats-service/ -v --cov=services/stats-service --cov-report=term-missing
```

### รัน stats-service ด้วย Docker

```bash
docker build -t lab6-stats-service .
docker run -d -p 3000:3000 --name stats-api lab6-stats-service
```

รายละเอียดเพิ่มเติม: [`docker/README.md`](./docker/README.md)

---

## 🗺️ สรุปภาพรวมเส้นทางการพัฒนาตามราย Lab

| Lab / สัปดาห์ | หัวข้อหลัก (Topic) | รายละเอียดการดำเนินงานและหลักฐานเชิงวิศวกรรม | เอกสารและโค้ดที่เกี่ยวข้อง |
| --- | --- | --- | --- |
| **Lab 01–03** | **Requirements & User Personas** | • **Target Persona:** วิเคราะห์กลุ่มเป้าหมายผู้ใช้จริง เช่น "เมย์" (พนักงานบริษัท/นิสิต อายุ 27 ปี)<br>• **Problem Statement:** ขาดการวางแผนทางการเงิน ไม่ทราบสัดส่วนค่าใช้จ่ายจริง และเงินออมไม่บรรลุเป้าหมาย<br>• **Artifacts:** User Personas, User Stories พร้อม Acceptance Criteria, Definition of Done (DoD), Main User Scenarios และ Project Proposal | [`/docs/requirements/`](./docs/requirements/)<br>[`/docs/definition-of-done.md`](./docs/definition-of-done.md)<br>[`/docs/project-proposal.md`](./docs/project-proposal.md) |
| **Lab 04** | **System Modeling & Analysis** | • **System Design:** ออกแบบ Data Flow Diagrams (DFD) และ UML Class Diagrams สำหรับจำลองโครงสร้างข้อมูล Transactions, Goals, Budgets และ Financial Reports | [`/docs/architecture/uml_models.md`](./docs/architecture/uml_models.md) |
| **Lab 05** | **Architecture Decisions (ADR & C4)** | • **ADR:** เลือกสถาปัตยกรรม **Modular Monolith** เพื่อความรวดเร็วในการส่งมอบ MVP ภายใน 8 สัปดาห์ และบันทึกการเลือก Tech Stack (React, Node.js + Express, PostgreSQL/Supabase)<br>• **C4 Model:** จัดทำ C4 Level 1 (Context Diagram) และ Level 2 (Container Diagram) | [`/docs/architecture/adr/`](./docs/architecture/adr/)<br>[`/docs/architecture/tech_stack.md`](./docs/architecture/tech_stack.md)<br>[`/docs/architecture/diagrams/`](./docs/architecture/diagrams/) |
| **Lab 06** | **Containerization & Docker Strategy** | • **Multi-stage Build:** สร้าง Production-Ready Dockerfile โดยเลือกใช้ Base Image `python:3.12-alpine` ที่มีขนาดเล็ก (~50-60 MB) ลด Attack Surface และเพิ่มความเร็วในการ Deploy<br>• **Security & Isolation:** รัน Container ด้วย Non-root User (`nobody`), แยก Stateless Service (`stats-service`) ออกเป็นเอกเทศ และเปิดพอร์ต 3000 | [`Dockerfile`](./Dockerfile)<br>[`/docker/README.md`](./docker/README.md)<br>[`/services/stats-service/`](./services/stats-service/) |
| **Lab 07–08** | **Feature MVP Development (Sprint)** | • พัฒนา Frontend ต้นแบบ 6 หน้า โดยฟังก์ชันหลัก 4 ส่วน:<br>&nbsp;&nbsp;1. **Dashboard:** สรุป 4 การ์ดสำคัญ (รายรับ, รายจ่าย, เงินคงเหลือ, ยอดออม) + Donut/Bar Chart<br>&nbsp;&nbsp;2. **Transactions:** บันทึกรายรับ-รายจ่ายย้อนหลังพร้อมสัญลักษณ์หมวดหมู่<br>&nbsp;&nbsp;3. **Goals:** การ์ดออมเงิน คำนวณเงินและระยะเวลาที่เหลือให้อัตโนมัติ<br>&nbsp;&nbsp;4. **Budgets:** ตั้งงบประมาณเปรียบเทียบยอดใช้จริง<br>• Wireframe และ Prototype ของ Sprint 1 เก็บไว้ในโฟลเดอร์ prototypes | [`/frontend/`](./frontend/)<br>[`/prototypes/sprint1/`](./prototypes/sprint1/) |
| **Lab 09** | **Automated Testing & TDD** | • **Core Business Logic Testing:** เขียน Unit Test สำหรับฟังก์ชัน `calculateAndFormatStats`<br>• **Techniques:** ประยุกต์ Equivalence Partitioning และ Boundary Value Analysis บนอินพุตขอบเขต (-1, 0, 1) และการปัดเศษ (9/4, 10/4, 11/4)<br>• **Property-Based Testing:** ใช้ `fast-check` ร่วมกับ Vitest และทำ Saboteur Testing ตรวจจับบั๊กจากการเปลี่ยน `Math.round` เป็น `Math.floor` | [`/tests/`](./tests/)<br>[`/docs/testing/lab9-test-design.md`](./docs/testing/lab9-test-design.md)<br>[`/docs/saboteur-journal.md`](./docs/saboteur-journal.md)<br>[`reflect.md`](./reflect.md) |
| **Lab 10** | **DevOps & CI/CD Pipeline** | • **GitHub Actions** 2 workflows:<br>&nbsp;&nbsp;1. `ci.yml` — Lint ด้วย `ruff` และรัน `pytest` พร้อม Coverage บน `services/stats-service/` (Python 3.12) เมื่อ Push/PR เข้า `main`<br>&nbsp;&nbsp;2. `test.yml` — ติดตั้งด้วย `npm ci`, รัน `npm test` และตรวจ Coverage Threshold (Statements/Branches ≥ 90%) ทุกครั้งที่ Push และ PR<br>• กำหนด Pipeline และ Container เป็นโค้ด (Workflow YAML + Dockerfile) เพื่อให้สร้างสภาพแวดล้อมซ้ำได้ | [`ci.yml`](./.github/workflows/ci.yml)<br>[`test.yml`](./.github/workflows/test.yml)<br>[`Dockerfile`](./Dockerfile) |
| **Lab 11** | **Security & Defensive Programming** | • **Pragmatic Paranoia (Tip 43):** ตรวจสอบ Input ฝั่ง Client เช่น จำนวนเงินต้องมากกว่า 0, ยอดต้องไม่ติดลบ, ต้องเลือกวันที่ และกันชื่อหมวดซ้ำ<br>• **Data Protection:** Escape ข้อความด้วยฟังก์ชัน `esc()` ก่อนแสดงผลเพื่อป้องกัน XSS (OWASP) | [`frontend/js/app.js`](./frontend/js/app.js)<br>[`frontend/js/goals.js`](./frontend/js/goals.js)<br>[`frontend/js/budget.js`](./frontend/js/budget.js) |
| **Lab 12** | **Refactoring & Code Quality** | • กำจัด Code Smells, ปรับแต่งโครงสร้างโค้ดเพื่อลด Complexity และลด Context Switching ของทีม | [`/docs/refactoring-journal.md`](./docs/refactoring-journal.md)<br>[`/src/`](./src/) |
| **Lab 12B** | **Safety Net Sprint** | • จัดทำชุดทดสอบครอบคลุม 21 รายการ จาก 3 ไฟล์ทดสอบ ครอบคลุมกรณี Happy Path, Edge Cases, Errors, Regression และ Property-Based Tests จนได้ **Test Coverage 100% ครอบคลุมทั้ง Statements, Branches, Functions และ Lines** | [`/docs/safety-net.md`](./docs/safety-net.md)<br>[`reflect.md`](./reflect.md) |
| **Lab 13–14** | **Working Software & Demo Readiness** | • เตรียมระบบและข้อมูลทดสอบ (Demo Data) สำหรับ Demo Day ตามโครงสร้าง 3-Act (Hook → Solution → Live Walkthrough)<br>• วางแผนสำรอง (Backup Plan) เช่น Hotspot, Local Container และ Screencast เมื่อระบบพังกลางคัน<br>• Frontend เปิดใช้งานได้ทันทีโดยไม่ต้องมี server และมีบัญชีทดลอง | [`/frontend/README.md`](./frontend/README.md) |
| **Lab 15** | **Ethics, PDPA & Final Reflection** | • **Data Minimization:** เก็บรวบรวมเฉพาะข้อมูลธุรกรรมตัวเลขที่จำเป็นตามกฎหมาย PDPA 2562 (ไม่เก็บ PII ที่เกินจำเป็น)<br>• **AI Disclosure:** เปิดเผยการใช้ AI ช่วยงานอย่างโปร่งใส<br>• **Open Source:** เผยแพร่ผลงานด้วย **MIT License** และจัดทำ Final Reflection รายบุคคล | [`AI_USAGE.md`](./AI_USAGE.md)<br>[`/docs/reflections/`](./docs/reflections/)<br>[`LICENSE`](./LICENSE) |

---

## ✅ User Stories ที่รองรับ

รายละเอียดและ Acceptance Criteria (Given/When/Then) ทั้งหมดอยู่ที่ [`user-stories.md`](./docs/requirements/user-stories.md)

| User Story | หน้าที่รองรับ |
| --- | --- |
| US-01 ดูสรุปรายรับ-รายจ่ายประจำเดือน | [Dashboard](./frontend/pages/dashboard.html) |
| US-02 ดูกราฟค่าใช้จ่ายตามหมวดหมู่ | [Dashboard](./frontend/pages/dashboard.html) |
| US-03 ติดตามเป้าหมายการออม | [เป้าหมาย](./frontend/pages/goals.html) |
| US-06 กำหนดงบประมาณรายเดือน | [งบประมาณ](./frontend/pages/budget.html) |
| US-04 รับการแจ้งเตือนค่าใช้จ่าย (Should) | ⏳ ยังไม่ได้พัฒนา |

---

## 📐 สถาปัตยกรรมระบบ (System Architecture & Diagrams)

โปรเจกต์นี้ออกแบบตามมาตรฐาน C4 Model — รายละเอียดเพิ่มเติมที่ [`/docs/architecture`](./docs/architecture/)

### 1. C4 Model: System Context (Level 1)

![C4 Level 1 - System Context](./docs/architecture/diagrams/c4-level-1-context.png)

### 2. C4 Model: Container Diagram (Level 2)

![C4 Level 2 - Container Diagram](./docs/architecture/diagrams/c4-level-2-container.png)

### 📑 Architectural Decision Records (ADRs)

* [ADR-001: Selection of Core Technology Stack](./docs/architecture/adr/0001-tech-stack-selection.md)
* [ADR-001: Modular Monolith vs Microservices](./docs/architecture/adr/0001-monolith-vs-microservices.md)
* [ADR-001: Use RESTful API for Internal Communication](./docs/architecture/adr/001-use-restful-api-internal-commu.md)

---

## 🧪 การทดสอบระบบและความเสถียร (Testing & Quality Assurance)

โปรเจกต์นี้ให้ความสำคัญกับความถูกต้องของการคำนวณทางการเงิน โดยมี Safety Net ครอบคลุมทุกการทำงาน:

```bash
# JavaScript: Unit + Property-based tests ด้วย Vitest และ fast-check
npm test
npm run test:coverage

# Python: stats-service ด้วย pytest
pytest services/stats-service/ -v --cov=services/stats-service
```

### สรุปผลการทดสอบ (Lab 12B Safety Net)

* **จำนวนเคสทดสอบ:** 21 รายการ (จาก 3 ไฟล์ทดสอบ)
* **Statements / Branches / Functions / Lines Coverage:** 100% ทุกด้าน

รายละเอียดอ่านได้ที่ [`/docs/safety-net.md`](./docs/safety-net.md)

---

## 🛡️ จรรยาบรรณวิชาชีพ ความเป็นส่วนตัว และ AI (Ethics & PDPA Compliance)

1. **Data Minimization & Privacy by Design (PDPA 2562):** ระบบจัดเก็บเฉพาะข้อมูลที่จำเป็นต่อการประมวลผลการเงินเท่านั้น ไม่เก็บข้อมูลส่วนบุคคลระบุตัวตน (PII) เกินความจำเป็น
2. **AI Disclosure & Transparency:** บันทึกประวัติคำสั่ง (Prompts) และผลลัพธ์จากการใช้งาน AI (เช่น OpenAI Codex) อย่างโปร่งใสใน [`AI_USAGE.md`](./AI_USAGE.md) และผ่านการตรวจสอบโดยมนุษย์ (Human-in-the-loop)
3. **Intellectual Honesty:** ผลงานสร้างขึ้นด้วยความรับผิดชอบ และเผยแพร่ภายใต้สัญญาอนุญาตแบบเปิดเผยซอร์สโค้ด

---

## ℹ️ เกี่ยวกับโปรเจกต์ (About & Credits)

* **พัฒนาโดย:** ทีม `se-sec1-team-07` — สาขาวิชาวิศวกรรมซอฟต์แวร์ (Software Engineering), มหาวิทยาลัยพะเยา
* **วิชา:** Software Engineering (225311)
* ข้อมูลสมาชิกแต่ละคน: [`/team/`](./team/)

---

## 📄 ใบอนุญาต (License)

โปรเจกต์นี้เผยแพร่ภายใต้ใบอนุญาต **[MIT License](./LICENSE)**
