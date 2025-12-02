# LL_Spec — สเปกมาตรฐาน Land Lens (Reflex801)

## บทนำ
เอกสารฉบับนี้กำหนดมาตรฐานเชิงเทคนิคสำหรับระบบ Land Lens (LL)  
เพื่อให้ทุกส่วนของ Human Land (HL) เชื่อมโยงกันได้อย่างถูกต้อง โปร่งใส และตรวจสอบย้อนกลับได้

---

## 1. โครงสร้างข้อมูลหลักของ Land Lens
### 1.1 Point Signals
- หน่วยข้อมูลจุดเดี่ยวที่เกิดจากภาพ/เสียง/ข้อความ
- ใช้ใน RAW → Overlay → Annotated

### 1.2 Area Signals
- การรวมกลุ่มจุดตามพื้นที่จริง
- สำหรับวิเคราะห์เชิงพื้นที่ (Spatial Intelligence)

### 1.3 LL Metadata
ฟิลด์บังคับ:
- LL_ID  
- Timestamp  
- HL_Source (เช่น HumanLand RAW)  
- Device  
- GPS / Location  
- Hash256  

---

## 2. Workflow มาตรฐาน (LL Pipeline)

1. RAW  
2. Overlay  
3. Annotated  
4. Export  
5. HL Integration  

แผนภาพไหล (Flow):

RAW → Overlay → Annotated → Export → HL_Core

---

## 3. Naming Convention
### ภาพ  
`LL_YYYYMMDD_locX_setX_vX.jpg`

### เอกสาร  
`LL_<Module>_<Type>_vX.md`

---

## 4. กฎความปลอดภัย
- ต้องมี Hash256 ทุกไฟล์ก่อนเข้าระบบ  
- ห้ามเขียนทับ RAW  
- Annotated ต้องมีผู้รับรอง (Custodian Sign)

---

## 5. การเชื่อมกับ Reflex801
Land Lens เป็น Layer L ของ 801  
เชื่อม Human Land (H) → Data Plane L → Ready → Deck / Research
