# LL_Spec — สเปกกลางโมดูลเลนส์แลนด์ (Land Lens Specification)

LL_Spec.md  
เวอร์ชัน: 1.0  
สถานะ: CORE SPEC (เชื่อม Human Land + Reflex801)

---

## 1. วัตถุประสงค์ของโมดูล Land Lens
Land Lens (LL) คือระบบสกัด “สัญญาณพื้นที่” จากภาพถ่ายจริง  
เพื่อสร้างข้อมูลเชิงพื้นที่ (Spatial Signal) ที่สามารถนำไปใช้ใน Reflex801  
เช่น เมือง / ตำบล / พื้นที่เศรษฐกิจ → กลายเป็นโหนดข้อมูลที่ใช้ทำงานได้ทันที

---

## 2. สถาปัตยกรรมหลัก (High-Level Architecture)

Input → Process → Output

### 2.1 Input Layer
- ภาพดิบจากพื้นที่ (HL_RAW_IMAGES/)
- ภาพ Overlay (LL_Overlay/)
- ภาพ Annotated (LL_Annotated/)
- จุดสัญญาณ (LL_PointSignals/)
- พื้นที่สัญญาณ (LL_AreaSignals/)

### 2.2 Processing Layer
- Normalization มาตรฐานภาพ
- Landmark Detection
- Spatial Tagging
- Pattern Match กับ HL_Tags.json
- Generate Signal Vector (LL_Vector)

### 2.3 Output Layer
- LL_Export/ → ใช้กับ Deck / Report
- LL_SignalMap.json → แผนที่สัญญาณ
- LL_Profile.md → โปรไฟล์พื้นที่มาตรฐาน

---

## 3. โครงสร้างไฟล์ภายในโมดูล LL

```
LL/
 ├── LL_Index.md
 ├── LL_Index_Base.md
 ├── LL_Spec.md        ← (ไฟล์นี้)
 ├── LL_Overlay/
 ├── LL_Annotated/
 ├── LL_PointSignals/
 ├── LL_AreaSignals/
 ├── LL_Export/
 └── DEV Pack + Workspace
```

---

## 4. มาตรฐานการกำกับคุณภาพ (LL Quality Rules)

### 4.1 Integrity Rules
- ห้ามปรับแต่งภาพแบบผิดความจริง
- ใช้ metadata ต้นฉบับทุกครั้ง
- ไฟล์ต้องผ่านการ hash ก่อนเก็บลง MASTER

### 4.2 Structure Rules
- ชื่อไฟล์ต้องตาม Format:  
  `[YYYYMMDD]_LL_[AreaCode]_[vX].jpg`

### 4.3 Versioning Rules
- ทุกการแก้ไขต้องมีไฟล์คู่  
  `*_changeset.json`

---

## 5. การเชื่อมต่อกับ Human Land (HL)

HL ให้ “บริบทมนุษย์”  
LL ให้ “สัญญาณพื้นที่”

เวลารวมกัน → ได้ข้อมูลแบบ Reflex801 (Human + Land + Time)

ตัวอย่าง Mapping:

| HL Layer | LL Layer | ผลลัพธ์ |
|---------|----------|----------|
| อาคาร | ภาพ Overlay | โหนดพื้นที่เศรษฐกิจ |
| เสียงตลาด | รูปแบบจราจร | พฤติกรรมพื้นที่ |
| ร้านค้า | ป้าย–จุดสัญญาณ | Market Signature |

---

## 6. การส่งออก (Export Standard)

ไฟล์ export ทุกชนิดต้องประกอบด้วย:

- ภาพ (LL_Export/)
- ใบอธิบายโหนด .md
- LL_Vector.json
- SHA256.txt (บังคับ)

---

## 7. ใช้ใน Reflex801 อย่างไร?

LL เป็น 1 ใน 3 Core Field Engines:

1. HL — Human Land  
2. LL — Land Lens  
3. VL — Voice Lens (อนาคต)

LL ทำให้ Reflex801 มองพื้นที่เป็นข้อมูล ไม่ใช่แค่ภาพ  
