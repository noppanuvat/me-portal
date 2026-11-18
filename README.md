# meturr-portal

หน้า Landing Portal หลักของ Meturr (https://meturr.online) เป็นหน้าเว็บสแตติกไฟล์เดียว (`index.html`) ออกแบบดาร์กโมด มีตัวเลือกบัตรสองใบเพื่อเข้าสู่ระบบย่อยต่างๆ

## คุณสมบัติ

- **บัตร Jira AI Analyzer** — เชื่อมไปยัง https://jira.meturr.online ระบบวิเคราะห์ Requirement ด้วย AI สรุปและตรวจสอบคุณภาพงาน
- **บัตร Jira Doc Creator** — เชื่อมไปยัง https://jira-create.meturr.online ระบบสร้าง Subtask และเอกสาร Confluence พร้อมกันในขั้นตอนเดียว
- **พื้นหลังอนิเมชัน** — Canvas วาดอนุภาคลอยตัวเชื่อมเส้นกันตอบสนองต่อตัวเมาส์
- **วิดเจ็ตเครดิต OpenRouter** — ดึงยอดเครดิตคงเหลือจาก `/api/openrouter/credits` (ผ่าน meturr-auth) แสดงเป็นแถบ進度และตัวเลข
- **รองรับมือถือ** — เลย์เอาต์สองคอลัมน์บนจอกว้าง เหลือคอลัมน์เดียวบนจอแคบ

## โครงสร้างไฟล์

```
meturr-portal/
└── index.html    # หน้าเว็บทั้งหมด รวม HTML, CSS, JavaScript ในไฟล์เดียว
```

## วิธีใช้งาน

เนื่องเป็นไฟล์สแตติก สามารถเปิด `index.html` ด้วยเบราว์เซอร์ได้ทันที หรือเสิร์ฟผ่านเว็บเซิร์ฟเวอร์ใดๆ เช่น Caddy, Nginx

ตัวอย่างการเสิร์ฟด้วย Caddy:

```caddyfile
meturr.online {
    root * /path/to/meturr-portal
    file_server
    encode gzip
}
```

หมายเหตุ: ฟีเจอร์วิดเจ็ตเครดิตต้องการเซิร์ฟเวอร์ `meturr-auth` ทำงานที่ `localhost:3002` และมี Caddy ตั้งค่า `forward_auth` ไว้แล้ว

## ภาษา

หน้าเว็บใช้ภาษาไทยเป็นหลัก (`lang="th"`)

---

สร้างและดูแลโดย **คุณนพ (noppanuvat)** 🌸
