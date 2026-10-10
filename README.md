
# 💰 Dashboard Personal Planning (Personal Finance Dashboard)

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![Build Status](https://img.shields.io/badge/build-passing-brightgreen.svg)]()
[![Test Coverage](https://img.shields.io/badge/coverage-90%25-green.svg)]()

> **Dashboard Personal Planning** คือเว็บแอปพลิเคชันบริหารจัดการการเงินส่วนบุคคลที่ช่วยติดตามรายรับ-รายจ่าย วางแผนเป้าหมายการออมเงิน ควบคุมงบประมาณประจำเดือน และแสดงผลสรุปทางการเงินได้จบในที่เดียว

---

## 👥 ทีมผู้พัฒนา (Team Members - `se-sec1-team-07`)

* **ขวัญชีวา คำแดง** — GitHub: [@67024728](https://github.com/67024728)
* **รัตน์ติญาภรณ์ แหลมจัด** — GitHub: [@BEAMMMMMMMMM1234](https://github.com/BEAMMMMMMMMM1234)
* **พณิชพล สุวรรณหล้า** — GitHub: [@Mokub112](https://github.com/Mokub112)
* **วีรยา เกี๋ยงคำ** — GitHub: [@67021264Wirayakiangkham](https://github.com/67021264Wirayakiangkham) *(Testing, DevOps & Documentation Specialist)*

---

## 🗺️ สรุปภาพรวมเส้นทางการพัฒนา 15 สัปดาห์ (Labs Overview)

| สัปดาห์ / Lab | หัวข้อการเรียนรู้ & สิ่งที่ทำในโปรเจกต์ | เอกสารที่เกี่ยวข้อง |
| :--- | :--- | :--- |
| **Lab 1–3** | **Requirements & User Personas:** วิเคราะห์ปัญหาผู้ใช้, กำหนด User Personas และ Main Scenarios | `/docs/requirements` |
| **Lab 4–6** | **System Architecture & Design:** ออกแบบ Architecture Diagram, C4 Model และ ADR (Architecture Decision Records) | `/docs/architecture` |
| **Lab 7–8** | **Sprint & Development:** พัฒนาฟังก์ชันหลัก (Dashboard, Transactions, Goals, Budgets) | `src/` |
| **Lab 9** | **Automated Testing:** เขียน Unit & Integration Test ด้วย Vitest และ fast-check (Coverage >= 90%) | `tests/` |
| **Lab 10** | **DevOps & CI/CD:** ตั้งค่า CI/CD Pipeline สำหรับการ Deploy อัตโนมัติและการตรวจเช็กคุณภาพโค้ด | `.github/workflows` |
| **Lab 11** | **Security & Defensive Programming:** ทำ Input Validation, OWASP Security Check และ Graceful Degradation | `src/utils/validation` |
| **Lab 12** | **Refactoring & Code Quality:** จัดการ Code Smell, แก้ไข Technical Debt และปรับปรุง Code Quality | `src/` |
| **Lab 13–14**| **Working Software & Demo Readiness:** ทดสอบ End-to-End, จัดทำ Demo Data และเตรียมแผนสำรองสำหรับ Demo Day | `/docs/demo` |
| **Lab 15** | **Professional Ethics & Final Reflection:** ประยุกต์ใช้ PDPA, Data Minimization, MIT License, เปิดเผย AI Usage และทำ Final Reflection | `/docs/final-reflection-*.md` |

---

## 🎯 ความต้องการของระบบและผู้ใช้ (Requirements & User Personas)

### 👤 User Personas Summary
* **เป้าหมายผู้ใช้:** นิสิตและคนทำงานที่ต้องการบริหารจัดการเงินส่วนตัวอย่างเป็นระบบ ต้องการเห็นภาพรวมค่าใช้จ่าย รู้ยอดเงินคงเหลือ และควบคุมไม่ให้ใช้เงินเกินงบประมาณ
* **ปัญหาเดิม (Pain Points):** ไม่รู้ว่าเงินหายไปไหน ใช้เงินเกินงบโดยไม่รู้ตัว ขาดวินัยในการเก็บเงินออม

### 🎬 Main User Scenarios
1. **บันทึกรายการ (Transactions):** ผู้ใช้บันทึกรายรับ/รายจ่าย แยกตามหมวดหมู่ (เช่น ค่าอาหาร, ค่าเดินทาง, ค่าที่พัก)
2. **วางแผนงบประมาณ (Budgets):** กำหนดงบประมาณประจำเดือนแยกตามหมวดหมู่ แล้วคอยเช็กกราฟเปรียบเทียบยอดใช้จ่ายจริง
3. **ติดตามเป้าหมาย (Savings Goals):** ตั้งเป้าหมายออมเงิน (เช่น ดาวน์รถ, เที่ยวญี่ปุ่น) และติดตามจำนวนเงินคงเหลือพร้อมวันที่ต้องออมให้ครบ
4. **สรุปภาพรวม (Dashboard):** ตรวจสอบยอดเงินคงเหลือ ยอดออมสะสม และดูสัดส่วนรายจ่ายผ่าน Donut Chart บน Dashboard

*(ดูรายละเอียดเอกสารเต็มได้ที่โฟลเดอร์ `/docs/requirements`)*

---

## 🌟 ฟีเจอร์หลักของระบบ (Key Features)

1. **📊 Dashboard:** แสดงสรุปตัวเลข 4 ช่องสำคัญ (รายรับ, รายจ่าย, เงินคงเหลือ, ยอดออมสะสม) พร้อมกราฟ Bar Chart และ Donut Chart แสดงสัดส่วนรายจ่าย
2. **📝 รายรับ-รายจ่าย (Transactions):** ฟอร์มบันทึกการเงินและประวัติรายการย้อนหลัง
3. **🎯 เป้าหมายการออม (Goals):** การ์ดแสดงเป้าหมาย คำนวณจำนวนเงินและจำนวนวันที่เหลือให้อัตโนมัติ
4. **💡 งบประมาณ (Budgets):** กำหนดงบประมาณรายเดือนพร้อมกราฟเปรียบเทียบยอดใช้จริง

---

## 🧪 การทดสอบระบบและการรันโปรเจกต์ (Lab 9: Automated Testing & Running)

ธุรกิจโลจิกส่วนการคำนวณได้รับการทดสอบด้วย **Vitest** และ **fast-check**

```bash
# 1. ติดตั้ง dependencies
npm install

# 2. ติดตั้งแบบ CI-style สำหรับสภาพแวดล้อมที่ตรงตาม lockfile
npm ci

# 3. รัน Unit & Integration Tests
npm test

# 4. ตรวจสอบ Test Coverage (เกณฑ์ Statement/Branch coverage >= 90%)
npm run test:coverage

# 5. เปิดรันระบบในโหมด Development
npm run dev

```

---

## 🛡️ จรรยาบรรณวิชาชีพ ความเป็นส่วนตัว และ AI (Ethics, PDPA & AI Disclosure)

* **Data Minimization & Privacy by Design (PDPA 2562):** เก็บรวบรวมเฉพาะข้อมูลตัวเลขธุรกรรมที่จำเป็นต่อการคำนวณเท่านั้น ไม่มีการเก็บข้อมูลส่วนบุคคลที่ระบุตัวตนได้เกินความจำเป็น
* **AI Disclosure:** เปิดเผยและบันทึกประวัติการใช้งาน AI ช่วยในการพัฒนาซอฟต์แวร์อย่างโปร่งใสในไฟล์ `/docs/AI_USAGE.md`
* **Defensive Programming & Security (OWASP):** ออกแบบระบบให้รองรับการ Validation ข้อมูลทั้งฝั่ง Client และ Server เพื่อป้องกันข้อมูลผิดพลาดหรืออันตรายตามหลัก Pragmatic Paranoia

---

## 📄 ใบอนุญาต (License)

โปรเจกต์นี้เผยแพร่ภายใต้ใบอนุญาต **[MIT License](https://www.google.com/search?q=LICENSE)** (Permissive Open Source License)

```

---

### 📌 ทำไมการใส่ตารางรวมสัปดาห์ (Lab 1–15) ถึงดีมาก?
1. **อาจารย์ตรวจง่าย:** อาจารย์เห็นทันทีว่าทีมทำครบทุกกระบวนการตั้งแต่สัปดาห์ที่ 1 ถึง 15
2. **เป็นพอร์ตโฟลิโอที่ดี:** เวลาคนภายนอกหรือผู้ว่าจ้างมาเปิดดู GitHub จะเห็นว่าซอฟต์แวร์ชิ้นนี้ถูกสร้างขึ้นอย่างเป็นระบบตามหลัก Software Engineering จริงๆ ครับ!

```
