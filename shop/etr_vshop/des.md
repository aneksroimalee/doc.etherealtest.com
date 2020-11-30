### Features!
 - ใช้งานง่าย ดีกว่าใช้ esx menu default เดิมๆหลายเท่า
 - แสดงค่า สถานะของรถ 
 - แต่งสีรถได้
 - เรียงลำดับตามราคาได้ ช่วยประกอบการตัดสินใจได้ดี
 - search box สำหรับค้นหาชื่อรถ
 - แสดงเงินผู้เล่นขณะเลือกซื้อรถ 
 - เลือก วิธีการจ่ายเงินได้ ว่าจะจ่ายด้วย เงินธนาคาร หรือ เงินสด 
 - ป้องกันการ สแปม เมื่อเงินไม่พอ(ลดการทำงานเซิฟเวอร์)
 - source code ของ esx_vehicleshop จะแก้ไขได้เหมือนเดิมทุกอย่าง
 - ใช้ ฐานข้อมูลเดิม ไม่ต้องแก้ไขอะไร
 - ตั้งค่าได้ หรือ จะไม่ก็ได้นะ
---

### การตั้งค่า

> ทุกการตั้งค่าถ้าไม่มีจะใช้ค่าเดิมของมัน

| ตัวแปร    | ประเภทข้อมูล   | ค่าเดิม | รายระเอียด | 
| -------- | -------- | -------- | -------- |
| prefix | string | `esx_vehicleshop` | ชื่อนำหน้าสำหรับ Event<br/>`>esx_vehicleshop<:buyVehicle`|
| payment     | string | `money`     | วิธีจ่ายเงินเมื่อซื้อรถ<br/>`money` `bank`    |
| disables     | string in array | เปิดทุกฟังชั่น     | ปิดใช้งานบางฟังชั่น<br/> `search` `sortprice` `changepayment` `color` `state` |
| blocks     | string or number in array | เปิดทุกอย่าง | บล็อกไม่ให้ใช้งานบางอัน<br/> เช่น ไม่ให้ใช้สีโครม     |
| desc     | object | ไม่มี     | คำอธิบายสำหรับบางอย่าง |
##### ตัวอย่าง `config.json`
```json
{
  "disables": ["state"],  
  "blocks": {
    "color": ["pink", 120] 
  },
  "payment": "bank",
  "prefix": "esx_vehicleshop", 
  "desc": {
    "category": {
      "super": "รถแรงๆ",
      "motorcycles": "มอเตอไซโก๋ๆ",
      "sports": "รถสุดแพง",
      "sportsclassics": "รถคลาสสิคสุดโก๋",
      "sedans": "รถธรรมดาๆ",
      "suvs": "รถคันใหญ่เบิ้มๆ",
      "offroad": "สำหรับสายลุย",
      "compacts": "คอมแพค",
      "coupes": "คูเป้"
    },
    "model": {
      "akuma": "มอไซสุดเฟี้ยว",
      "kuruma2": "รถกันกระสุน"
    }
  }
}

```
> ❌ ห้าม  comment ใน `config.json` อาจจะ error เอาได้
