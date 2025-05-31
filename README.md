# Exploratory Data Analysis (EDA) in Excel
## Project Facebook Page Performance Comparison
Project นี้เปรียบเทียบ 2 pages ทาง Facebook โดยมีขั้นตอนดังนี้

- import files dramaadd, ejeab, engagement
  - dramaadd ประกอบด้วย columns create_date, create_time, type, message, link, page
  - ejeab ประกอบด้วย columns create_date, create_time, type, message, link, page
  - engagement ประกอบด้วย columns id, reactions, comments, shares

- Data Preparation
  - Join 3 Tables: ทำการรวมข้อมูลจากไฟล์ dramaadd, ejeab, และ engagement เข้าเป็นตาราง Master เดียวกันโดยใช้ฟังก์ชัน VLOOKUP
  - Feature Engineering:
    - ดึงวันในสัปดาห์จากวันที่โพส (WEEKDAY): สร้าง Column ใหม่เพื่อระบุวันในสัปดาห์ (จันทร์-อาทิตย์, โดยกำหนดให้วันอาทิตย์เป็น 1)
    - ดึงชั่วโมงที่โพส (HOUR): สร้าง Column ใหม่เพื่อระบุชั่วโมงที่โพส
    - วิเคราะห์คำพูดติดปาก: ใช้ฟังก์ชัน SEARCH เพื่อค้นหาคำว่า "555", "ถถถ", "มอนิ่ง" ใน Column message ซึ่งเป็นคำพูดติดปากของเพจ dramaadd และ ejeab

- EDA (Pivot Table and Visualization)
  - One Variable (เน้นดูผลรวมของทั้ง 2 pages)
    - เปรียบเทียบการโพส ของ 2 pages ว่าใครโพสเยอะกว่ากัน (เป็นสัดส่วน)
    - หาการกระจายตัวของ Reactions, Commends, Shares
    - หาการกระจายตัวของการ Post ว่าอยู่ในช่วงเวลาไหนบ้าง (HOUR)
    - ตรวจสอบดูการใช้คำว่า "555" ใน message มีการใช้บ่อยแค่ไหน เป็นสัดส่วนใช้กับไม่ใช้เป็นเท่าไร
  - Two Variable (เน้นการเปรียบเทียบ)
    - เปรียบเทียบการกระจายตัวของ Reactions, Commends, Shares โดยใช้ Box plot
    - เปรียบเทียบเวลาการ Post ของทั้ง 2 pages ว่ามีสัดส่วนเท่าไรในแต่ละชั่วโมง โดยใช้ Data Bars ใน Pivot Table
    - เปรียบเทียบเวลาการ Post ของทั้ง 2 pages ว่ามีสัดส่วนเท่าไรในแต่ละชั่วโมง โดยใช้ 100% Stacked Bar Chart
    - เปรียบเทียบวันที่ Post ของทั้ง 2 pages ว่ามีสัดส่วนเท่าไรในแต่ละวัน โดยใช้ 100% Stacked Bar Chart
    - เปรียบเทียบ message ที่ใช้คำว่า "555" ของทั้ง 2 pages ว่ามีสัดส่วนเท่าไร โดยใช้ 100% Stacked Bar Chart
    - เปรียบเทียบ message ที่ใช้คำว่า "ถถถ" ของทั้ง 2 pages ว่ามีสัดส่วนเท่าไร โดยใช้ 100% Stacked Bar Chart
    - เปรียบเทียบ message ที่ใช้คำว่า "มอนิ่ง" ของทั้ง 2 pages ว่ามีสัดส่วนเท่าไร โดยใช้ 100% Stacked Bar Chart
   
  - Summary
    - ejeab post มากกว่า dramaadd เพียงแค่เล็กน้อยมาก ๆ 50.10% : 49.90%
    - ค่าเฉลี่ยของ Reactions ของ ejeab มีมากกว่า dramaadd 25,385 : 4,406
    - ค่าเฉลี่ยของ Commends ejeab มีมากกว่า dramaadd 773 : 221
    - ค่าเฉลี่ยของ Shares ejeab มีมากกว่า dramaadd 783 : 446
    - การ Post ejeab จะเน้น Post ช่วงเช้ามืดถึงช่วงเช้า 3.00-9.00น. ส่วน dramaadd จะเน้น Post ช่วงหัวค่ำถึงช่วงดึก 19.00-23.00น.
    - การ Post ในแต่ละสัปดาห์ กระจายการ Post ในแต่ละวัน ใกล้ ๆ กันทั้ง 2 pages 
    - ejeab จะใช้คำพูดติดปากเป็น "555" และ dramaadd จะใช้คำพูดติดปากเป็น "ถถถ" (ใช้ภาษาไทยในการพิมพ์กับใช้ภาษาอังกฤษในการพิมพ์ ในปุ่มคีย์บอร์ดเดียวกัน)
    - ejeab จะใช้คำสวัสดีเป็น "มอนิ่ง" ส่วน dramaadd จะไม่ใช้คำนี้เลย
