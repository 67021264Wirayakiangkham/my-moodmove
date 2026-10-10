# 💰 Dashboard Personal Planning (Personal Finance Dashboard)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](./LICENSE)
[![CI](https://github.com/se-sec1-team-07/personal-finance-dashboard/actions/workflows/ci.yml/badge.svg)](https://github.com/se-sec1-team-07/personal-finance-dashboard/actions/workflows/ci.yml)

> **Dashboard Personal Planning** คือเว็บแอปพลิเคชันบริหารจัดการการเงินส่วนบุคคลแบบครบวงจร ช่วยติดตามรายรับ-รายจ่าย วางแผนเป้าหมายการออมเงิน ควบคุมงบประมาณประจำเดือน และแสดงผลสรุปทางการเงินผ่าน Interactive Dashboard ในแพลตฟอร์มเดียว

## 🎬 Demo

![Demo ของ Personal Finance Dashboard](./docs/demo/demo.gif)

---

## 👥 ทีมผู้พัฒนา (Team Members - `se-sec1-team-07`)

* **ขวัญชีวา คำแดง** — GitHub: [@67024728](https://github.com/67024728)
* **รัตน์ติญาภรณ์ แหลมจัด** — GitHub: [@BEAMMMMMMMMM1234](https://github.com/BEAMMMMMMMMM1234)
* **พณิชพล สุวรรณหล้า** — GitHub: [@Mokub112](https://github.com/Mokub112)
* **วีรยา เกี๋ยงคำ** — GitHub: [@67021264Wirayakiangkham](https://github.com/67021264Wirayakiangkham) *(Testing, DevOps & Documentation Specialist)*

---

## 🚀 วิธีการติดตั้งและรันโปรเจกต์ (Quick Setup)

```bash
# 1. Clone repository
git clone https://github.com/se-sec1-team-07/personal-finance-dashboard.git
cd personal-finance-dashboard

# 2. ติดตั้ง dependencies ตาม lockfile
npm ci

# 3. รัน Unit & Integration Tests พร้อมตรวจ Coverage
npm run test:coverage

# 4. เปิดรันระบบในโหมด Development
npm run dev
```

📘 คู่มือการใช้งานฉบับเต็ม: [`USER_GUIDE.md`](./docs/USER_GUIDE.md)

---

## 🗺️ สรุปภาพรวมเส้นทางการพัฒนาตามราย Lab

| Lab / สัปดาห์ | หัวข้อหลัก (Topic) | รายละเอียดการดำเนินงานและหลักฐานเชิงวิศวกรรม | เอกสารและโค้ดที่เกี่ยวข้อง |
| --- | --- | --- | --- |
| **Lab 01–03** | **Requirements & User Personas** | • **Target Persona:** วิเคราะห์กลุ่มเป้าหมายผู้ใช้จริง เช่น "เมย์" (พนักงานบริษัท/นิสิต อายุ 27 ปี)<br>• **Problem Statement:** ขาดการวางแผนทางการเงิน ไม่ทราบสัดส่วนค่าใช้จ่ายจริง และเงินออมไม่บรรลุเป้าหมาย<br>• **Artifacts:** จัดทำ User Personas, Definition of Done (DoD), Main User Scenarios และ Project Proposal | [`/docs/requirements/`](./docs/requirements/)<br>[`/docs/proposal.md`](./docs/proposal.md) |
| **Lab 04** | **System Modeling & Analysis** | • **System Design:** ออกแบบ Data Flow Diagrams (DFD) และ UML Class Diagrams สำหรับจำลองโครงสร้างข้อมูล Transactions, Goals, Budgets และ Financial Reports | [`/docs/architecture/uml_models.md`](./docs/architecture/uml_models.md) |
| **Lab 05** | **Architecture Decisions (ADR & C4)** | • **ADR-001:** เลือกสถาปัตยกรรม **Modular Monolith** (Node.js + Express + Supabase/PostgreSQL) เพื่อความรวดเร็วในการส่งมอบ MVP ภายใน 8 สัปดาห์ และรองรับ ACID Transactions ข้อมูลการเงินได้อย่างถูกต้อง<br>• **C4 Model:** จัดทำ C4 Level 1 (Context Diagram) และ Level 2 (Container Diagram) เพื่อแยกแยะการทำงานระหว่าง React Frontend, Node.js Backend API และ PostgreSQL Database | [`/docs/architecture/adr/`](./docs/architecture/adr/)<br>[`/docs/architecture/diagrams/`](./docs/architecture/diagrams/) |
| **Lab 06** | **Containerization & Docker Strategy** | • **Multi-stage Build:** สร้าง Production-Ready Dockerfile โดยใช้ Node.js Alpine Base Image ขนาดเล็ก ลด Attack Surface และเพิ่มความเร็วในการ Deploy<br>• **Security & Isolation:** กำหนดสิทธิ์ Non-root User (`appuser`) ตามหลัก ESP §7, แยก Stateless Service (`stats-service`) ออกเป็นเอกเทศ และเปิดพอร์ต 3000 ชัดเจน | [`/docs/architecture/tech_stack.md`](./docs/architecture/tech_stack.md)<br>[`Dockerfile`](./Dockerfile) |
| **Lab 07–08** | **Feature MVP Development (Sprint)** | • พัฒนาฟังก์ชันหลัก 4 ส่วน:<br>&nbsp;&nbsp;1. **Dashboard:** สรุป 4 การ์ดสำคัญ (รายรับ, รายจ่าย, เงินคงเหลือ, ยอดออม) + Donut/Bar Chart<br>&nbsp;&nbsp;2. **Transactions:** บันทึกรายรับ-รายจ่ายย้อนหลังพร้อมสัญลักษณ์หมวดหมู่<br>&nbsp;&nbsp;3. **Goals:** การ์ดออมเงิน คำนวณเงินและระยะเวลาที่เหลือให้อัตโนมัติ<br>&nbsp;&nbsp;4. **Budgets:** ตั้งงบประมาณเปรียบเทียบยอดใช้จริง | [`src/components/`](./src/components/)<br>[`src/services/`](./src/services/) |
| **Lab 09** | **Automated Testing & TDD** | • **Core Business Logic Testing:** เขียน Unit Test สำหรับฟังก์ชัน `calculateAndFormatStats`<br>• **Techniques:** ประยุกต์ Equivalence Partitioning และ Boundary Value Analysis บนอินพุตขอบเขต (-1, 0, 1) และการปัดเศษ (9/4, 10/4, 11/4)<br>• **Property-Based Testing:** ใช้ `fast-check` ร่วมกับ Vitest และทำ Saboteur Testing ตรวจจับบั๊กจากการเปลี่ยน `Math.round` เป็น `Math.floor` | [`tests/unit/`](./tests/unit/)<br>[`reflect.md`](./reflect.md) |
| **Lab 10** | **DevOps & CI/CD Pipeline** | • ตั้งค่า **GitHub Actions Workflow** ตรวจสอบการรัน `npm ci`, `npm test` และเช็ก Coverage Threshold อัตโนมัติทุกครั้งที่มี Push และ Pull Request<br>• **IaC:** กำหนดสภาพแวดล้อมการรันด้วย `docker-compose.yml` ให้สร้างระบบซ้ำได้ในคำสั่งเดียว | [`.github/workflows/ci.yml`](./.github/workflows/ci.yml)<br>[`docker-compose.yml`](./docker-compose.yml) |
| **Lab 11** | **Security & Defensive Programming** | • **Pragmatic Paranoia (Tip 43):** ออกแบบ Input Validation ทั้งฝั่ง Client และ Server ป้องกันค่า Negative/Invalid Inputs<br>• **Data Protection:** ใช้วิธี Sanitize ข้อมูลเพื่อป้องกัน OWASP Security Flaws | [`src/utils/validation.js`](./src/utils/validation.js) |
| **Lab 12** | **Refactoring & Code Quality** | • กำจัด Code Smells, ปรับแต่งโครงสร้างโค้ดเพื่อลด Complexity และลด Context Switching ของทีม | [`src/`](./src/) |
| **Lab 12B** | **Safety Net Sprint** | • จัดทำชุดทดสอบครอบคลุม 21 รายการ จาก 3 ไฟล์ทดสอบ ครอบคลุมกรณี Happy Path, Edge Cases, Errors และ Property-Based Tests จนได้ **Test Coverage 100% ครอบคลุมทั้ง Statements, Branches, Functions และ Lines** | [`/docs/safety-net.md`](./docs/safety-net.md)<br>[`reflect.md`](./reflect.md) |
| **Lab 13–14** | **Working Software & Demo Readiness** | • เตรียมระบบและข้อมูลทดสอบ (Demo Data) สำหรับ Demo Day ตามโครงสร้าง 3-Act (Hook → Solution → Live Walkthrough)<br>• วางแผนสำรอง (Backup Plan) เช่น Hotspot, Local Container และ Screencast เมื่อระบบพังกลางคัน | [`/docs/demo/`](./docs/demo/) |
| **Lab 15** | **Ethics, PDPA & Final Reflection** | • **Data Minimization:** เก็บรวบรวมเฉพาะข้อมูลธุรกรรมตัวเลขที่จำเป็นตามกฎหมาย PDPA 2562 (ไม่เก็บ PII ที่เกินจำเป็น)<br>• **AI Disclosure:** เปิดเผยการใช้ AI ช่วยงานอย่างโปร่งใส<br>• **Open Source:** เผยแพร่ผลงานด้วย **MIT License** และจัดทำ Final Reflection รายบุคคล | [`/docs/AI_USAGE.md`](./docs/AI_USAGE.md)<br>[`/docs/`](./docs/) (ไฟล์ `final-reflection-*.md`) |

---

## 📐 สถาปัตยกรรมระบบ (System Architecture & Diagrams)

โปรเจกต์นี้ออกแบบตามมาตรฐาน C4 Model — รายละเอียดเพิ่มเติมที่ [`/docs/architecture`](./docs/architecture/)

### 1. C4 Model: System Context (Level 1)

![C4 Level 1 - System Context](./docs/architecture/diagrams/c4-level1-context.png)

### 2. C4 Model: Container Diagram (Level 2)

![C4 Level 2 - Container Diagram](./docs/architecture/diagrams/c4-level2-container.png)

### 📑 Architectural Decision Records (ADRs)

* **ADR-001:** [Selection of Core Technology Stack](./docs/architecture/adr/0001-tech-stack-selection.md)

---

## 🧪 การทดสอบระบบและความเสถียร (Testing & Quality Assurance)

โปรเจกต์นี้ให้ความสำคัญกับความถูกต้องของการคำนวณทางการเงิน โดยมี Safety Net ครอบคลุมทุกการทำงาน:

```bash
# รัน Unit & Integration Tests ด้วย Vitest
npm test

# ตรวจสอบเปอร์เซ็นต์ Coverage
npm run test:coverage
```

### สรุปผลการทดสอบ (Lab 12B Safety Net)

* **จำนวนเคสทดสอบ:** 21 รายการ (จาก 3 ไฟล์ทดสอบ)
* **Statements / Branches / Functions / Lines Coverage:** 100% ทุกด้าน

รายละเอียดอ่านได้ที่ [`/docs/safety-net.md`](./docs/safety-net.md)

---

## 🛡️ จรรยาบรรณวิชาชีพ ความเป็นส่วนตัว และ AI (Ethics & PDPA Compliance)

1. **Data Minimization & Privacy by Design (PDPA 2562):** ระบบจัดเก็บเฉพาะข้อมูลตัวเลขธุรกรรมที่จำเป็นต่อการประมวลผลการเงินเท่านั้น ไม่มีการจัดเก็บข้อมูลส่วนบุคคลระบุตัวตน (PII) ที่เกินความจำเป็น
2. **AI Disclosure & Transparency:** บันทึกประวัติคำสั่ง (Prompts) และผลลัพธ์จากการใช้งาน AI (เช่น OpenAI Codex) อย่างโปร่งใสใน [`/docs/AI_USAGE.md`](./docs/AI_USAGE.md) และผ่านการตรวจสอบโดยมนุษย์ (Human-in-the-loop)
3. **Intellectual Honesty:** ผลงานสร้างขึ้นด้วยความรับผิดชอบ และเผยแพร่ภายใต้สัญญาอนุญาตแบบเปิดเผยซอร์สโค้ด

---

## ℹ️ เกี่ยวกับโปรเจกต์ (About & Credits)

* **พัฒนาโดย:** ทีม `se-sec1-team-07` — สาขาวิชาวิศวกรรมซอฟต์แวร์ (Software Engineering), มหาวิทยาลัยพะเยา
* **วิชา:** Software Engineering

---

## 📄 ใบอนุญาต (License)

โปรเจกต์นี้เผยแพร่ภายใต้ใบอนุญาต **[MIT License](./LICENSE)**
