# Note
ฉันกำลังพัฒนาเว็บด้วย Next.js (App Router/Pages Router: [ระบุ]) และใช้ Supabase เป็น backend (Postgres + RLS [ถ้ามี]) เป้าหมาย:
1) สแกนโครงสร้างโปรเจกต์ทั้งหมดและสรุปสถาปัตยกรรม (routing, data-flow, auth, state management)
2) สร้าง “DB health checks” เพื่อทดสอบว่าเชื่อมต่อได้/มีตารางสำคัญ/ดึงข้อมูลได้ พร้อม error handling และคำสั่งทดสอบ
3) ตรวจและปรับปรุงโค้ดฝั่ง client/server ให้ใช้ Supabase อย่างถูกต้อง (อย่าเผย service role key ฝั่ง client)
4) ช่วยออกแบบ/ปรับสไตล์หน้าเว็บให้สวย ใช้ [Tailwind CSS/Chakra UI/shadcn/ui/อื่นๆ] ตาม best practice
ข้อมูลที่ควรรู้:
- ไฟล์ Supabase client: [ระบุไฟล์เช่น lib/supabase/server.ts และ lib/supabase/client.ts]
- เพจ/route ที่เกี่ยวข้อง: [pages หรือ app/route ที่สำคัญ]
- สคีมาฐานข้อมูล: [วางสรุปตาราง/คอลัมน์สำคัญ หรือแนบลิงก์ไฟล์ schema.sql]
ข้อกำหนดผลลัพธ์:
- ให้รายการไฟล์ที่จะแก้/เพิ่ม พร้อมโค้ดเต็ม
- ระบุวิธีรัน/ทดสอบเป็นคำสั่ง (npm/yarn) และ curl/Postman ตัวอย่าง
- ถ้ามีความคลุมเครือ ให้ถามกลับก่อนลงมือ
โปรดตรวจโค้ดที่เรียก Supabase ทั้งหมดเพื่อ:
- แยกโค้ด client vs server อย่างถูกต้อง (ห้ามใช้ service role ใน client)
- ตรวจ RLS policy/anon key อธิบายสาเหตุ error ที่พบบ่อย และวิธีแก้
- แสดง flowchart หรือ checklist การไล่ปัญหา
สร้างตัวอย่าง:
- server action หรือ route handler ที่ดึงข้อมูลจากตาราง [ระบุ], รองรับ pagination/sorting
- ฮุค/utility ฝั่ง client สำหรับ fetch + แคช (เช่น React Query/SWR) พร้อมตัวอย่างเพจที่แสดงผล และ error/empty states
- unit/integration test ขั้นต่ำ (ถ้าเป็นไปได้) พร้อมคำสั่งรัน
ปรับแต่ง UI ให้สวยงาม
ฉันใช้ [Tailwind/shadcn/ui/Chakra/ฯลฯ] โปรด:
- เสนอ design tokens (สี/spacing/typography)
- สร้าง component UI ที่นำกลับมาใช้ใหม่ (เช่น Card, Button, Table, EmptyState)
- แปลงหน้าปัจจุบัน [ระบุไฟล์หน้า] ให้ใช้ component เหล่านี้ พร้อม responsive และ accessibility (focus states, aria-attrs)

- ขอผลลัพธ์ “ทำตามได้ทันที”: ให้รวมโค้ดเต็มไฟล์ + คำสั่งรัน/ทดสอบ + ตัวอย่าง request/response
