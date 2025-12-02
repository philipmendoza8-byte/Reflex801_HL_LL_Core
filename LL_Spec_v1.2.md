# LL_Spec v1.1 — Land Lens Technical Specification (Reflex801)

> Repository: Reflex801_HL_LL_Core  
> Module: Land Lens (LL) — มาตรฐานเชิงเทคนิค  
> Status: Base Spec v1.1 (DEV Draft)

---

## หมวดที่ 1 — ภาพรวม Land Lens (LL)

Land Lens (LL) = มาตรฐานสำหรับอ่าน “สภาพพื้นที่จริง” จากภาพสนาม  
โดยใช้ควบคู่กับ Human Land (HL) เพื่อให้ Reflex801 เข้าใจบริบทเมือง / ตลาด / เส้นทางเดินจริง

**วัตถุประสงค์ของ LL**

1. แยก “ข้อมูลพื้นที่” ออกจาก “ข้อมูลคน” อย่างชัดเจน  
2. ทำให้ทุกภาพจากสนามสามารถ  
   - ถูกอ่านซ้ำได้ (reproducible)  
   - นำไปเทียบเคียงกันข้ามเวลา / ข้ามเมืองได้  
3. สร้างภาษากลางให้ทีมภาคสนาม, ทีมวิเคราะห์, และ LLM ใช้ชุดคำเดียวกัน  
4. วางฐานสำหรับการทำ Dashboard, LLM-Agent, และ Data Pack ของ Reflex801 ในอนาคต  

**ความสัมพันธ์ HL / LL**

- **HL (Human Land)**  
  โฟกัส “คน + อารมณ์ + บริบท” ที่อยู่ในพื้นที่
- **LL (Land Lens)**  
  โฟกัส “พื้นที่ + โครงสร้าง + เส้นทาง + ป้าย + แสง + layout”  
- ทั้งสองโมดูลต้องใช้ **ภาพชุดเดียวกัน** แต่คนละเลนส์ในการตีความ  
- ทุกไฟล์ LL ต้องอ้างอิงกลับไปที่รหัส HL เดียวกันได้เสมอ (ผ่าน Index)

> Core Rule: LL ไม่เก็บข้อมูลส่วนบุคคล (PDPA) — เก็บเฉพาะ pattern ของ “พื้นที่ + สิ่งแวดล้อม”

---

## หมวดที่ 2 — โครงสร้างมาตรฐาน Land Lens (Folder + Naming)

Land Lens ใช้โครงเดียวกับ DEV Structure แต่เน้นฝั่ง “พื้นที่” เป็นหลัก  

### 2.1 โครงโฟลเดอร์หลัก (ภายใต้ `LL_DEV_Workspace/`)

- `LL_RAW_IMAGES/`  
  - ภาพดิบจากภาคสนาม (ยังไม่แต่ง / ไม่ใส่ overlay)  
- `LL_Overlay/`  
  - ไฟล์ overlay / blueprint / เส้นกำกับจุดสนใจ (ซ้อนทับ RAW)  
- `LL_Annotated/`  
  - ไฟล์ภาพหรือ layer ที่มีข้อความกำกับ เช่น จุดขาย, จุดตัน, จุดเสี่ยง  
- `LL_Export/`  
  - output สำหรับ Deck, Report, Dashboard  
- `LL_Index_Base.md`  
  - ฐาน index สำหรับ mapping ระหว่างภาพ / โฟลเดอร์ / เขตพื้นที่  
- `LL_Index.md`  
  - index เวอร์ชันใช้งานจริงสำหรับ Land Lens Module  
- `LL_Spec_v1.1.md`  
  - เอกสารมาตรฐานฉบับนี้ (spec เวอร์ชัน 1.1)

### 2.2 มาตรฐานการตั้งชื่อไฟล์ (File Naming)

Format หลักสำหรับไฟล์ภาพ LL:

`[YYYYMMDD]_LL_[AreaCode]_[SpotID]_[ShotID]_vX.ext`

ตัวอย่าง:

- `20251202_LL_UTR-SCHOOL_A01_S001_v1.jpg`  
- `20251202_LL_UTR-SCHOOL_A01_S001_v1_overlay.png`  

**คำอธิบาย**

- `YYYYMMDD`  = วันที่เก็บข้อมูล (ตามเวลาประเทศไทย)  
- `LL`        = โมดูล Land Lens  
- `AreaCode`  = รหัสพื้นที่ย่อย (เช่น UTR-SCHOOL, BKK-MARKET-01)  
- `SpotID`    = จุดยืน/มุมกล้อง (A01, A02, …)  
- `ShotID`    = ลำดับรูปในจุดนั้น (S001, S002, …)  
- `vX`        = เวอร์ชันการประมวลผล (v1 = ดิบ, v2 = แต่งแสง, v3 = annotated)  

> Core Rule: ห้ามใช้ชื่อไฟล์ลอย ๆ เช่น `IMG_1234.jpg` ใน workspace 801  
> ทุกไฟล์ต้องถูกแปลงชื่อให้เข้าระบบก่อนเข้า repo หรือก่อนแชร์ให้ทีมอื่น

### 2.3 Tag & Metadata (ย่อสำหรับ v1.1)

- Metadata ขั้นต่ำต่อ 1 ภาพ LL:
  - `capture_time`
  - `area_code`
  - `spot_id`
  - `shot_id`
  - `device` (เช่น iPhone, Mirrorless, ActionCam)
- ไฟล์ tag สามารถเก็บในรูป:
  - `LL_Tags.json` (global)  
  - `LL_Tags_[AreaCode].json` (เช่น `LL_Tags_MorningMarket.json`)

---

> Version: LL_Spec v1.1  
> Status: Base Spec (2 หมวดแรก — Ready for commit)
