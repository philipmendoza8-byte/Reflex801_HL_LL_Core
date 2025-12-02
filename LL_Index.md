# LL_Index — Land Lens Module (Reflex801)

## วัตถุประสงค์
Land Lens (LL) คือมาตรฐานการอ่านพื้นที่ “สัญญาณทางสังคม”  
ใช้กับภาพตลาดเช้า ตลาดเย็น ถนน ผู้คน ร้านค้า พื้นที่เมือง–ชนบท  
เป็นชุดช้อนสัญญาณเพื่อใช้งานกับ Reflex801

---

## #1 เอกสารหลัก (อยู่ใน “แพ็กพัฒนา”)

1. `DEV_Integrity.docx`
   - กติกาและความหมายของชุดข้อมูล LL
   - วิธีเช็กความสมบูรณ์ของข้อมูลภาคสนาม

2. `DEV_Structure.docx`
   - โครงสร้างมาตรฐานของ Land Lens
   - โฟลเดอร์: `LL_RAW_IMAGES/`, `LL_Overlay/`, `LL_Annotated/`, `LL_Export/`

3. `DEV_Usage.docx`
   - วิธีใช้งาน LL ใน context ต่าง ๆ
   - วิธีเช็ก field/data ว่าผ่านมาตรฐานหรือไม่

4. `DEV_Summary.docx`
   - ภาพรวมชุด Land Lens ใช้ประกอบใน Deck

5. `DEV_Versioning.docx`
   - กติกากำกับเวอร์ชัน การตั้งชื่อ commit  
   - ไฟล์ checksum LL

---

## #2 โครงสร้างมาตรฐาน Land Lens (อ้างอิงจาก DEV_Structure)

### `LL_RAW_IMAGES/`
ภาพดิบจากภาคสนาม ไม่มี overlay

### `LL_Overlay/`
ไฟล์ overlay / blueprint / annotation

### `LL_Annotated/`
ภาพที่ผ่านการช้อนสัญญาณแล้ว พร้อม tag ระบุความหมาย

### `LL_Export/`
รูปภาพที่พร้อมใช้ใน Deck / Report

### `LL_Index.md`
ไฟล์นี้ ใช้เป็นรายการ mapping + อธิบายโครงสร้างฝั่ง LL

> หมายเหตุ: field repo ภาคสนามจะเก็บแยกในโครงจริง  
> repo นี้เก็บเฉพาะโครงสร้าง ไม่เก็บ RAW เพื่อผ่าน PDPA

---

## #3 วิธีใช้ LL_Core ในโปรเจกต์ภาคสนาม

1. สร้างโฟลเดอร์ เช่น `Reflex801_LL_Field_North`
2. คัดลอกโครงสร้างจาก `DEV_Structure.docx`
3. วางไฟล์ `LL_Index.md` ไปที่โฟลเดอร์งาน
4. ตรวจ source version
5. พร้อมทำงาน

---

## #4 มาตรฐานสำคัญ
- ไม่เก็บข้อมูลส่วนบุคคล
- ไม่เก็บภาพแบบชี้ตัวบุคคล
- ไฟล์ต้องคงความ “สนาม” ไม่ดัดแปลงผิดความจริง
- ชุดข้อมูลต้องเชื่อมกลับ PDPA ของ Reflex801

---

## Metadata
> Version: LL_Index v1.0  
> Status: Base Structure Ready  
> Maintainer: Reflex801 (Land Lens Module)

---

Add_LL_Index v1
