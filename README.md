# week6-lab

## ตั้งค่าฐานข้อมูล

ทั้ง `moviehub` และ `kitchen` ใช้ตัวแปร environment ชื่อ `DATABASE_URL`
ร่วมกัน ให้คัดลอกไฟล์ตัวอย่างแล้วใส่รหัสผ่านในเครื่องเท่านั้น:

```bash
cp .env.example .env
```

จากนั้นโหลดค่าก่อนรันโปรแกรม (เปลี่ยนค่า `YOUR-PASSWORD` ในคำสั่งให้เป็น
รหัสผ่านจริงโดยไม่บันทึกลง Git):

```bash
export DATABASE_URL='postgresql://postgres.qklgcgwrvmdobottyjvn:YOUR-PASSWORD@aws-0-ap-southeast-1.pooler.supabase.com:5432/postgres?sslmode=require'
export JWT_SECRET='ใช้ค่าลับเฉพาะเครื่องที่ยาวอย่างน้อย 32 ตัวอักษร'
export ALLOWED_ORIGINS='http://localhost:5173'
```

รัน MovieHub:

```bash
cd moviehub
go run .
```

หรือรัน Kitchen:

```bash
cd kitchen
go run .
```

อย่ารันทั้งสอง service พร้อมกันบนพอร์ต `:8080` เดียวกัน และอย่า commit ไฟล์
`.env` หรือรหัสผ่านจริงขึ้น repository