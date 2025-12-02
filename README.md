# Reflex801_HL_LL_Core

**Reflex801 HL_LL Core**  
แพ็กหลักสำหรับเก็บ _โครงสร้างมาตรฐาน_ ของ Human Land (HL) และ Land Lens (LL)  
ใช้เป็น **ชุดต้นแบบ** เวลาไปติดตั้งระบบ Reflex801 บนเครื่อง / เมือง / ทีมอื่น ๆ

---

## 1. โครงแพ็ก

โฟลเดอร์หลักในรีโปนี้:

- `แพ็คพัฒนา/`  
  > DEV Pack – รวมเอกสาร Word สำหรับออกแบบ, integrity, structure, summary, usage, versioning  
  - `DEV_Integrity.docx`  
  - `DEV_Structure.docx`  
  - `DEV_Summary.docx`  
  - `DEV_Usage.docx`  
  - `DEV_Versioning.docx`

- `LL_DEV_พื้นที่ทำงาน/`  
  > LL DEV Workspace – เขตทดลอง / ปรับแต่ง Land Lens  
  - `LL_A_CLEAN.docx`  
  - `LL_B_CLEAN.docx`  
  - `LL_C_CLEAN.docx`  
  - `README_LL_DEV.docx`  
  - `ReleaseNote_LL_v1.1.docx`  
  - `SHA256_LL_DEV.docx`

- `ที่เก็บ_เริ่มต้น/`  
  > Initial Store – จุดเก็บไฟล์ index แบบ MD สำหรับเชื่อมโลก dev (Word) กับโลกระบบ (Git)  
  - `HL_Index.md`  ← index ของ Human Land  
  - `LL_Index.md`  ← index ของ Land Lens  
  - ไฟล์อื่น ๆ ในอนาคต (เช่น config, map, manifest)

---

## 2. เป้าหมายของชุดนี้

1. **แยก “เนื้อหามาตรฐาน” ออกจาก “งานภาคสนาม”**  
   - repo นี้ถือเป็น **Core Spec**  
   - field-repo อื่น ๆ จะดึง pattern จากที่นี่ไปใช้

2. ใช้เป็น **แพ็กติดตั้งครั้งแรก** สำหรับเครื่องใหม่ / ทีมใหม่  
   - โหลด zip จาก GitHub  
   - แตกไฟล์ → เปิดดู DEV Pack (Word) → อ่าน index (MD)  
   - แล้วจึงค่อยนำไปประกอบกับ RAW / READY ของสนามจริง

3. ทำให้ **HL / LL** มีภาษากลางร่วมกัน  
   - Human Land = ภาพ/เสียง/อารมณ์ภาคสนาม  
   - Land Lens = เลนส์ตีความ + tag + test vectors

---

## 3. การอ่านไฟล์

1. เริ่มจากโฟลเดอร์ `แพ็คพัฒนา/`
   - เปิด `DEV_Summary.docx` เพื่อดูภาพรวม  
   - ตามด้วย `DEV_Structure.docx` และ `DEV_Usage.docx`

2. จากนั้นดู index แบบสั้นใน
   - `ที่เก็บ_เริ่มต้น/HL_Index.md`  
   - `ที่เก็บ_เริ่มต้น/LL_Index.md`

3. ถ้าต้องการดูการเปลี่ยนแปลงเวอร์ชัน / checksum
   - เปิด `DEV_Versioning.docx`  
   - เปิด `SHA256_LL_DEV.docx`

---

## 4. เวอร์ชัน

- HL_LL Core Pack: **v1.0 (DEV Base Structure)**
- Release note: ดูไฟล์ `LL_DEV_พื้นที่ทำงาน/ReleaseNote_LL_v1.1.docx`

> หมายเหตุ: repo นี้โฟกัสที่ “สเปก” ไม่ใช่ data ภาคสนาม  
> ข้อมูล RAW/READY จากสนามจริงจะอยู่ในรีโป/ที่เก็บคนละชุดกัน
> Add README v1
