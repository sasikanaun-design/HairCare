# SHAMPOO CARE — Student landing page project

เว็บไซต์ตัวอย่างขายแชมพู 2 SKU พร้อมแบบฟอร์มสั่งซื้อ, Google Sheets backend, หน้ารายการคำสั่งซื้อ, สถานะหยิบ/แพ็ค และใบจ่าหน้าพัสดุสำหรับพิมพ์

## ไฟล์ในโปรเจกต์
- `index.html`, `style.css`, `app.js` — เว็บไซต์
- `assets/` — รูปสินค้าแยกโฟลเดอร์
- `apps-script.gs` — โค้ดเชื่อม Google Sheets

## ตั้งค่า Google Sheets
1. สร้าง Google Sheet ใหม่ ตั้งชื่อ `SHAMPOO CARE Orders`
2. เปิด Extensions > Apps Script
3. ลบโค้ดเดิม แล้ววางโค้ดจาก `apps-script.gs`
4. กด Save แล้วเลือกฟังก์ชัน `setup` และ Run ครั้งแรก เพื่ออนุญาตสิทธิ์และสร้างชีต Orders
5. Deploy > New deployment > เลือกประเภท Web app
6. Execute as: Me; Who has access: Anyone (สำหรับงานสาธิต)
7. Deploy และคัดลอก Web app URL ที่ลงท้าย `/exec`
8. เปิด `app.js` แล้วแทน `PASTE_YOUR_GOOGLE_APPS_SCRIPT_WEB_APP_URL_HERE` ด้วย URL จริง
9. Commit และ push ไฟล์ที่แก้แล้วขึ้น GitHub อีกครั้ง

> หมายเหตุ: การตั้งค่า Anyone ทำให้ endpoint รับคำสั่งซื้อได้โดยไม่ต้องล็อกอิน เหมาะกับงานสาธิตเท่านั้น ไม่ควรใช้กับข้อมูลลูกค้าจริงโดยไม่มีระบบป้องกันสแปมและมาตรการความปลอดภัยเพิ่มเติม

## นำขึ้น GitHub
1. สร้าง repository ใหม่ชื่อ `shampoo-care`
2. อัปโหลดไฟล์และโฟลเดอร์ทั้งหมดในโปรเจกต์นี้ (อย่าอัปโหลดไฟล์ ZIP อย่างเดียว)
3. Commit changes

## นำขึ้น Vercel
1. เข้า https://vercel.com และ Sign up ด้วย GitHub
2. กด Add New > Project แล้ว Import repository `shampoo-care`
3. Framework Preset เลือก Other; Build Command และ Output Directory เว้นว่าง
4. กด Deploy
5. ใช้ URL ที่ Vercel ให้มาเป็นลิงก์เว็บไซต์ส่งอาจารย์

## วิธีใช้งานระบบ
1. ลูกค้าเลือกสินค้าและกรอกข้อมูลในหน้าเว็บ
2. ระบบบันทึกออเดอร์ลง Google Sheets แท็บ Orders
3. เปิดส่วนจัดการคำสั่งซื้อ แล้วกดโหลดรายการ
4. ตรวจชื่อ/ที่อยู่/เบอร์โทร/สินค้า/จำนวน แล้วกดยืนยันหยิบสินค้า
5. ตรวจซ้ำก่อนกดยืนยันแพ็คสินค้า
6. กดพิมพ์ใบจ่าหน้า แล้วเลือกเครื่องพิมพ์หรือ Save as PDF

## ข้อจำกัดของต้นแบบ
- สต็อกสินค้าและการตัดสต็อกอัตโนมัติยังไม่ได้ทำ
- ระบบสถานะเป็นตัวอย่างสำหรับงานเรียน ยังไม่มีบัญชีผู้ดูแล/ล็อกอิน
- ใบจ่าหน้าเป็นเอกสารภายในร้าน ไม่ใช่ใบปะหน้าจากขนส่งและไม่มีบาร์โค้ดขนส่ง
