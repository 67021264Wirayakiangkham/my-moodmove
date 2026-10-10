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

## 🏛️ การตัดสินใจทางสถาปัตยกรรม (Architecture & ADR)
* **Modular Monolith Architecture:** พัฒนาด้วย Node.js + Express รวมส่วน Transaction, Reporting และ Recommendation Engine ไว้ใน Deployment Unit เดียวกัน เพื่อความรวดเร็วในการส่งมอบ MVP ใน 8 สัปดาห์ และจัดการ ACID Transactions ของข้อมูลการเงินได้อย่างปลอดภัย
* **Tech Stack Rationale:**
  * **Frontend (React):** มี Ecosystem ของ Charting Libraries (เช่น Recharts) ที่สมบูรณ์ ช่วยสร้าง Dashboard เปรียบเทียบรายจ่ายประจำเดือนให้ผู้ใช้เห็นภาพรวมได้ง่าย
  * **Backend (Node.js + Express):** ใช้ Full-stack JavaScript ลด Context Switching ในทีมและมี Non-blocking I/O ที่เพียงพอต่อการทำ CRUD
  * **Database (Supabase / PostgreSQL):** ใช้ Relational Database เพื่อความถูกต้องของข้อมูลการเงิน (ACID Compliance) และลดภาระการจัดการ Infrastructure

---

## 🐳 DevOps & Containerization Strategy
* **Production-Ready Dockerfile:** ใช้ `python:3.12-alpine` (หรือ Node image ตามบริการ) ควบคุมขนาด Image ให้เล็ก ใช้ Multi-stage build แยก dependency builder ออกจาก runtime และรันผ่าน Non-root user (`appuser`) เพื่อความปลอดภัย (ESP §7)
* **Service Decomposition:** แยกส่วนประมวลผลสถิติเป็น `stats-service` (Microservices pattern) ให้ทีมสามารถพัฒนาและ Deploy แยกอิสระได้

---

## 🧪 การทดสอบระบบ (Lab 9 & Lab 12B Safety Net)
ระบบผ่านการทดสอบอย่างเข้มข้นด้วย **Vitest** และ **fast-check** (Property-Based Testing) พร้อมเกณฑ์ Test Coverage สูงถึง **100%**
* **Unit Testing & TDD:** ทดสอบฟังก์ชัน Core Business Logic เช่น `calculateAndFormatStats` ผ่าน Equivalnce Partitioning และ Boundary Value Analysis
* **Property-Based Testing:** ใช้ `fast-check` ตรวจสอบ Invariant ของระบบ และป้องกันข้อผิดพลาดจากการปัดเศษ (Rounding errors)
* **Safety Net (Lab 12B):** ชุดทดสอบ 21 รายการครอบคลุม Edge Cases และ Regression tests ที่ช่วยสร้างความมั่นใจในการ refactor โค้ด

### คำสั่งในการติดตั้งและรันเทส:
```bash
# ติดตั้ง dependencies
npm install

# ติดตั้งแบบ CI-style
npm ci

# รัน unit tests
npm test

# ตรวจสอบ Test Coverage (เกณฑ์ Statement/Branch >= 90%)
npm run test:coverage
