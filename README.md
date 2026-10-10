
# 💰 Dashboard Personal Planning (Personal Finance Dashboard)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)]()
[![Test Coverage](https://img.shields.io/badge/coverage-100%25-green.svg)]()

> **Dashboard Personal Planning** คือเว็บแอปพลิเคชันบริหารจัดการการเงินส่วนบุคคลที่ช่วยติดตามรายรับ-รายจ่าย วางแผนเป้าหมายการออมเงิน ควบคุมงบประมาณประจำเดือน และแสดงผลสรุปทางการเงินได้จบในที่เดียว

---

## 👥 ทีมผู้พัฒนา (Team Members - `se-sec1-team-07`)
* **ขวัญชีวา คำแดง** — GitHub: [@67024728](https://github.com/67024728)
* **รัตน์ติญาภรณ์ แหลมจัด** — GitHub: [@BEAMMMMMMMMM1234](https://github.com/BEAMMMMMMMMM1234)
* **พณิชพล สุวรรณหล้า** — GitHub: [@Mokub112](https://github.com/Mokub112)
* **วีรยา เกี๋ยงคำ** — GitHub: [@67021264Wirayakiangkham](https://github.com/67021264Wirayakiangkham) *(Testing, DevOps & Documentation Specialist)*

---

## 🚀 วิธีการติดตั้งและรันโปรเจกต์ใน 5 บรรทัด (Quick Setup)
```bash
git clone [https://github.com/se-sec1-team-07/personal-finance-dashboard.git](https://github.com/se-sec1-team-07/personal-finance-dashboard.git)
cd personal-finance-dashboard
npm install
npm ci
npm run dev

```

---
## 📐 สถาปัตยกรรมระบบ (System Architecture - C4 Models)

รายละเอียดการออกแบบและตัดสินใจทางสถาปัตยกรรมของระบบ (ดูเอกสารฉบับเต็มได้ที่โฟลเดอร์ [`/docs/architecture`](./docs/architecture))

### 1. C4 Model: System Context (Level 1)
![System Context Diagram](./docs/architecture/diagrams/c4-level-1-context.png)

### 2. C4 Model: Container (Level 2)
![Container Diagram](./docs/architecture/diagrams/c4-level-2-container.png)

### Architectural Decision Records (ADRs)
- [ADR-001: Selection of Core Technology Stack](./docs/architecture/adr/0001-tech-stack-selection.md)

---

## 🗺️ สรุปภาพรวมเส้นทางการพัฒนาตามราย Lab (Labs & Artifacts)

| Lab / สัปดาห์ | หัวข้อหลัก (Topic) | รายละเอียดการดำเนินงานในโปรเจกต์ |
| --- | --- | --- |
| **Lab 01–03** | Requirements & Personas | วิเคราะห์ผู้ใช้ (เช่น "เมย์" อายุ 27 ปี), กำหนด User Personas และ Main User Scenarios |
| **Lab 04–06** | System Design & Docker | ออกแบบ C4 Model, จัดทำ ADR-001 และสร้าง Production-Ready Dockerfile |
| **Lab 07–08** | Sprint & Feature MVP | พัฒนา 4 แท็บหลัก: Dashboard, Transactions, Goals และ Budgets |
| **Lab 09 & 12B** | Automated Testing & Safety Net | เขียน Unit/Property-Based Tests ด้วย Vitest & fast-check ได้ Coverage **100%** |
| **Lab 10** | DevOps & CI/CD | ตั้งค่า GitHub Actions Workflow ตรวจสอบ Test และ Coverage อัตโนมัติ |
| **Lab 11 & 15** | Security, PDPA & Ethics | ทำ Input Validation (Pragmatic Paranoia), ปฏิบัติตาม PDPA และเปิดเผย AI Usage |

---

## 🧪 การทดสอบระบบ (Testing & Quality Assurance)

```bash
# รัน Unit & Property-Based Tests
npm test

# ตรวจสอบ Test Coverage (เกณฑ์ 100%)
npm run test:coverage

```

---

## ℹ️ เกี่ยวกับโปรเจกต์ (About / Help)

* **ทำโดย:** ทีม `se-sec1-team-07` — Software Engineering, ม.พะเยา
* **AI Disclosure:** บันทึกประวัติการใช้ AI อย่างโปร่งใสใน `/docs/architecture/AI_USAGE.md`

---

## 📄 ใบอนุญาต (License)

โปรเจกต์นี้เผยแพร่ภายใต้ใบอนุญาต **[MIT License](https://www.google.com/search?q=LICENSE)**

