# 📂 CRUD + Upload File

## 📝 โจทย์
สร้าง **REST API** สำหรับจัดการไฟล์ (CRUD + Upload) โดยใช้ **ภาษาใดก็ได้**  
(เช่น Node.js, Python, Java, Go, PHP, Rust ฯลฯ)

---

## ⚙️ Function ที่ต้องมี
1. **Upload File (Create)**  
   - อัปโหลดไฟล์เข้าสู่ระบบ  
   - เก็บไฟล์ได้ทั้งแบบ Local (`uploads/`) หรือ Cloud (เช่น S3)  
   - ต้องบันทึก **metadata** ของไฟล์ลง database เช่น  
     - `id`  
     - `filename` (ชื่อไฟล์ที่ระบบ generate เช่น `uuid.ext`)  
     - `original_name`  
     - `mime_type`  
     - `size`  
     - `created_at`  

2. **List Files (Read All)**  
   - return รายการไฟล์ทั้งหมดในรูปแบบ JSON array  

3. **Get File Detail (Read One)**  
   - return รายละเอียดไฟล์จาก `id`  

4. **Update File Metadata (Update)**  
   - update `original_name` โดยไม่ต้อง upload ไฟล์ใหม่  

5. **Delete File (Delete)**  
   - delete ทั้ง record ใน database และไฟล์จริงใน storage  

---

## ✅ Validation
- ประเภทไฟล์ที่อนุญาต: `pdf`, `docx`, `jpg`, `png`  
- ขนาดไฟล์สูงสุด: **5MB**  
- ต้องไม่ใช้ชื่อไฟล์ต้นฉบับตรง ๆ → ให้ rename เป็น `uuid.ext` เพื่อป้องกันไฟล์ซ้ำหรือ unsafe name  

---

## 🚀 การส่งงาน
- push code ขึ้น **GitHub** (public repo แนะนำ)  
- ใน repo ควรมี:
  - `README.md` อธิบายวิธี run project + ตัวอย่าง API call
  - `.env.example` สำหรับ environment variables (ถ้ามี)
  - script run (เช่น `npm run dev`, `make dev`, ฯลฯ)
  - ถ้ามี test → อธิบายวิธี run test (`npm test`, `pytest`, ฯลฯ)
- เสร็จแล้วส่ง **ลิงก์ GitHub repo** มาที่:  
  📧 `team@ddexpgroup.com`  

---

## 💡 Note
- ผู้สอบสามารถออกแบบ **endpoint, database schema, และโครงสร้าง code** ได้เองทั้งหมด  
- ใช้ **database อะไรก็ได้** (SQLite, PostgreSQL, MySQL, MongoDB ฯลฯ)  
- ถ้ามี **Unit Test** ครอบคลุม CRUD จะได้ bonus points  
- สิ่งที่ควรเน้น:
  - code อ่านง่าย  
  - โครงสร้างชัดเจน (เช่น แยก controller/service/repository)  
  - error handling + validation ครบถ้วน  
