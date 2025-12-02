# HL_Index — Human Land Module (Reflex801)

**บทบาท:**  
Human Land (HL) คือเลเยอร์ที่เก็บ “ของจริง” จากสนาม  
เช่น รูป, เสียง, ข้อความสั้น, บันทึกอารมณ์, สถานที่, เวลา  
ก่อนจะถูกส่งต่อให้ Land Lens (LL) วิเคราะห์ต่อ

รีโปนี้เก็บเฉพาะ **สเปกมาตรฐาน** ของ HL  
ไม่เก็บไฟล์ RAW ภาคสนามจริง

---

## 1. ชุดเอกสารอ้างอิง (อยู่ใน `แพ็คพัฒนา/`)

### 1. `DEV_Integrity.docx`
- ข้อตกลงเรื่องความถูกต้องของข้อมูล HL  
- วิธีตรวจสอบว่าภาพ/เสียง/ข้อความมาจากสนามจริง

### 2. `DEV_Structure.docx`
- โครงสร้างโฟลเดอร์ Human Land แบบมาตรฐาน  
- เช่น `HL_RAW_IMAGES/`, `HL_Overlay/`, `HL_Annotated/`, `HL_Export/`

### 3. `DEV_Usage.docx`
- วิธีใช้งาน Human Land ใน context ต่าง ๆ  
- วิธีให้ทีม field/ทีม data ใช้โฟลเดอร์ร่วมกันโดยไม่ชนกัน

### 4. `DEV_Summary.docx`
- ภาพรวม Human Land แบบอ่านรอบเดียวเข้าใจทันที  
- แนวคิด Reflex801 → HL → LL → Deck

### 5. `DEV_Versioning.docx`
- กติกา versioning, naming, commit message  
- ใช้กับ HL ทั้งหมด

---

## 2. โครง Human Land มาตรฐาน (สรุปจาก DEV_Structure)

- `HL_RAW_IMAGES/`  
  ภาพจากสนามแบบดิบ ยังไม่ใส่ overlay

- `HL_Overlay/`  
  ไฟล์ overlay / blueprint / annotation

- `HL_Annotated/`  
  ภาพที่ใส่หมายเหตุ อธิบาย จุดสนใจ สถานการณ์จริง

- `HL_Export/`  
  ชุดภาพที่พร้อมใช้ใน Deck / Report

- `HL_Index.md`  
  ไฟล์นี้เอง ใช้อธิบาย mapping + สเปกโครง HL

> หมายเหตุ: field repo ภาคสนามจะคัดลอกโครงนี้ไปใช้ แล้วเติม RAW จริงเข้าไป

---

## 3. วิธีนำ HL_Core ไปใช้ในรีโปภาคสนาม

1. สร้างรีโปใหม่ เช่น `Reflex801_HL_Field_North`
2. คัดลอกโครง HL ตาม `DEV_Structure.docx`
3. นำไฟล์ `HL_Index.md` เวอร์ชันนี้ไปวางในรีโปสนาม
4. ระบุ source version  
   ตัวอย่าง:
   
---

## 4. หมายเหตุสำคัญ

- รีโปนี้ไม่มีข้อมูลส่วนบุคคล  
- ไม่มีภาพจริงของสนาม  
- ใช้เพื่อออกแบบ/แยก “สเปก” ออกจากงานจริง  
- ข้อมูลจริงต้องเก็บในรีโปแยกตาม PDPA ของ Reflex801
Add HL_Index v1




