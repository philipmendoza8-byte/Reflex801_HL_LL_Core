# HL_Index — Human Land Module (Reflex801)

ไฟล์นี้ใช้เป็นดัชนีอ้างอิง / มาตรฐานการทำงานของ Human Land (HL)
ใช้เพื่อควบคุมโครงสร้าง, ความครบถ้วน, การใช้งาน และการเชื่อมโยง HL → LL → Deck

---

## #1 ชุดเอกสารมาตรฐาน (อ้างอิงไฟล์ใน `แพ็กพัฒนา/`)

### 1. `DEV_Integrity.docx`
- หลักการคงความสมบูรณ์ของข้อมูล HL  
- ข้อกำหนดเรื่องภาพ / เมือง / สถานการณ์จากสนามจริง

### 2. `DEV_Structure.docx`
- โครงสร้างไฟล์ Human Land มาตรฐาน  
- โฟลเดอร์ต่าง ๆ เช่น `HL_RAW_IMAGES/`, `HL_Overlay/`, `HL_Annotated/`, `HL_Export/`

### 3. `DEV_Usage.docx`
- วิธีใช้งาน HL ตาม context ต่าง ๆ  
- ใช้ไฟล์ field/data ยังไงให้รองรับการใช้งานในโมดูลอื่น

### 4. `DEV_Summary.docx`
- ภาพรวม Human Land แบบย่อเพื่องาน LL + Deck  
- สำหรับ Reflex801 HL → LL → Deck onboarding

### 5. `DEV_Versioning.docx`
- กฎการตั้งชื่อเวอร์ชัน, commit message  
- วิธีเก็บ checksum ของ HL แต่ละรุ่น

---

## #2 โครง Human Land มาตรฐาน (อ้างอิงจาก `DEV_Structure`)

- `HL_RAW_IMAGES/`  
  ภาพจากสนามแบบดิบ ยังไม่ overlay  

- `HL_Overlay/`  
  ไฟล์ overlay / blueprint / annotation  

- `HL_Annotated/`  
  ภาพที่มีหมายเหตุ อธิบาย สนาม / จุดสนใจ / สิ่งที่พบจริง  

- `HL_Export/`  
  รูปภาพพร้อมใช้สำหรับ Deck / Report  

- `HL_Index.md`  
  ไฟล์ดัชนี ใช้อธิบาย mapping ของโครง HL ทั้งหมด

> หมายเหตุ: field repo ภาพสนามจะถูกเก็บแยกใน RAW และค่อยย้ายเข้า repo เมื่อผ่าน PDPA

---

## #3 วิธีใช้ HL_Core ในโฟลเดอร์สนาม

1. สร้างโฟลเดอร์ เช่น `Reflex801_HL_Field_North`
2. คัดลอกโครง HL จาก `DEV_Structure.docx`
3. วางไฟล์ `HL_Index.md` ไว้ในโฟลเดอร์เป็นศูนย์กลางของระบบ
4. เช็ค source version
5. พร้อมทำงาน

---

## #4 มาตรฐานสำคัญ

- ไม่โยนไฟล์ข้อมูลส่วนบุคคล  
- ไม่เก็บภาพสนามแบบสุ่ม  
- ไฟล์ต้องตามโครง “สนาม” ห้ามกระจายตัว  
- ชุดข้อมูลต้องเชื่อมกลับ PDPA ของ Reflex801  

---

## Metadata
> Version: HL_Index v1.0  
> Status: Base Structure Ready  
> Maintainer: Reflex801 (Human Land Module)  

---

Add_HL_Index v1
