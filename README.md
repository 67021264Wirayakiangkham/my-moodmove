
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

## 🗺️ สรุปภาพรวมเส้นทางการพัฒนาตามราย Lab (Labs & Artifacts Overview)

| Lab / สัปดาห์ | หัวข้อหลัก (Topic) | รายละเอียดการดำเนินงานในโปรเจกต์ (Implementation & Artifacts) |
| :--- | :--- | :--- |
| **Lab 01–03** | **Requirements & User Personas** | วิเคราะห์ปัญหาผู้ใช้ (เช่น "เมย์" พนักงานบริษัทอายุ 27 ปี), กำหนด User Personas และ Main User Scenarios สำหรับการบันทึกการเงินและการตั้งเป้าหมาย |
| **Lab 04** | **System Analysis & Modeling** | ออกแบบโครงสร้างระบบ, Data Flow Diagrams และ UML Class Diagrams เพื่อรองรับระบบบริหารจัดการการเงิน |
| **Lab 05** | **Architecture Decisions (ADR & C4)** | ตัดสินใจเลือก **Modular Monolith Architecture** (Node.js + Express + Supabase/PostgreSQL) พร้อมจัดทำ C4 Model (Context & Container Diagram) |
| **Lab 06** | **Containerization & Docker** | สร้าง Production-Ready Dockerfile (Multi-stage build, Alpine image, Non-root `appuser`) และแยก Service สำหรับ stats-service |
| **Lab 07–08** | **Sprint & Feature Development** | พัฒนาฟังก์ชันหลัก 4 แท็บ: Dashboard, รายรับ-รายจ่าย (Transactions), เป้าหมาย (Goals) และงบประมาณ (Budgets) |
| **Lab 09** | **Automated Testing & TDD** | เขียน Unit Test ด้วย Vitest และ Property-Based Test ด้วย fast-check, ทำ TDD (Red-Green-Refactor) และ Saboteur Testing |
| **Lab 10** | **DevOps & CI/CD** | ตั้งค่า GitHub Actions Workflow ให้รัน `npm ci` และตรวจสอบ Test Coverage อัตโนมัติทุกครั้งที่มีการ Push และ PR |
| **Lab 11** | **Security & Defensive Programming** | ทำ Input Validation ทั้งฝั่ง Client และ Server (Pragmatic Paranoia) ป้องกันข้อมูลผิดพลาดและรักษาความปลอดภัยข้อมูลผู้ใช้ |
| **Lab 12** | **Refactoring & Technical Debt** | จัดการ Code Smell, ปรับปรุงสถาปัตยกรรมโค้ด และดูแลความสะอาดของ Source Code ให้มีคุณภาพสูง |
| **Lab 12B** | **Safety Net Sprint** | เพิ่มความมั่นใจด้วยชุดทดสอบครอบคลุม 21 รายการ (จาก 3 test files) ได้ผล Test Coverage **100% (Statements, Branches, Functions, Lines)** |
| **Lab 13–14** | **Working Software & Demo Readiness** | เตรียม Demo Data, ทดสอบระบบ End-to-End และวางแผนสำรองการนำเสนอ (Demo Backup Plan) |
| **Lab 15** | **Professional Ethics & Reflection** | ประยุกต์ใช้ PDPA (Data Minimization), เลือกใช้ MIT License, เปิดเผย AI Usage และจัดทำ Final Reflection |

---

## 🧪 การทดสอบระบบและการรันโปรเจกต์ (Commands)

```bash
# 1. ติดตั้ง dependencies
npm install

# 2. ติดตั้งแบบ CI-style
npm ci

# 3. รัน Unit & Integration Tests
npm test

# 4. ตรวจสอบ Test Coverage (เกณฑ์ผ่าน 100%)
npm run test:coverage

# 5. เปิดรันระบบในโหมด Development
npm run dev

```

---

## 🛡️ จรรยาบรรณ ความเป็นส่วนตัว และ AI (Ethics, PDPA & AI Disclosure)

* **Data Minimization (PDPA 2562):** เก็บเฉพาะข้อมูลตัวเลขธุรกรรมทางการเงินที่จำเป็นต่อการประมวลผล ไม่เก็บข้อมูลส่วนบุคคลเกินความจำเป็น
* **AI Disclosure:** บันทึกประวัติและเปิดเผยการใช้ AI ช่วยพัฒนาซอฟต์แวร์อย่างโปร่งใสใน `/docs/AI_USAGE.md`

## 📄 ใบอนุญาต (License)

โปรเจกต์นี้เผยแพร่ภายใต้ใบอนุญาต **[MIT License](https://www.google.com/search?q=LICENSE)**
