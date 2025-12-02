# LL_Index — Land Lens Module (Reflex801)

## บทนำ
Land Lens (LL) = ชุดเลนส์วิเคราะห์ “พื้นที่ / เมือง / สนามภาคสนาม”
ใช้คู่กับ Human Land (HL) เพื่อให้ระบบ Reflex801 มองภาพมนุษย์ + พื้นที่จริง

---

## #1 ชุดเอกสาร DEV Pack (อยู่ใน ‘แพ็คพัฒนา/’)

### 1. `DEV_Integrity.docx`
- กฎความสมบูรณ์ของข้อมูล LL
- วิธีเก็บข้อมูลภาคสนาม LL ให้ไม่ผิดเพี้ยน

### 2. `DEV_Structure.docx`
- โครงสร้างมาตรฐาน Land Lens
- โครงของ LL_RAW_IMAGES / LL_Overlay / LL_Annotated / LL_Export

### 3. `DEV_Usage.docx`
- วิธีใช้งาน Land Lens ในสถานการณ์ต่าง ๆ

### 4. `DEV_Summary.docx`
- ภาพรวมระบบ Land Lens สำหรับ Deck / Report

### 5. `DEV_Versioning.docx`
- แนวทางตั้งชื่อไฟล์, commit message, checksum

---

## #2 โครงสร้างโฟลเดอร์หลัก (Reference จาก DEV Structure)

### `LL_RAW_IMAGES/`
– ภาพดิบทั้งหมดจากภาคสนาม

### `LL_Overlay/`
– ไฟล์ Overlay สำหรับ blueprint / annotation

### `LL_Annotated/`
– ภาพที่ annotate เสร็จแล้ว พร้อมใช้ใน Deck

### `LL_Export/`
– output ส่งเข้าระบบ Reflex801

### `LL_Index.md`
– ไฟล์ index สำหรับ mapping LL ทั้งหมด

---

## #3 วิธีใช้งาน LL_Core ในโฟลเดอร์ภาคสนาม

1. สร้างโฟลเดอร์ เช่น `Reflex801_LL_Field_City`
2. คัดลอกโครง LL จาก `DEV_Structure.docx`
3. วางไฟล์ `LL_Index.md` ไว้ที่โฟลเดอร์กลางเพื่อเป็น index
4. เช็ค source version
5. พร้อมทำงาน

---

## #4 มาตรฐานสำคัญ

- ไม่เก็บข้อมูลส่วนบุคคล
- ไม่ถ่ายภาพบ้านเลขที่
- ไม่เก็บภาพคนแบบชัดเจน
- ชุดข้อมูลต้องสอดคล้อง PDPA

---

## Metadata
> Version: LL_Index v1.0  
> Status: Base Structure Ready  
> Maintainer: Reflex801 (Land Lens Module)

Add_LL_Index v1
