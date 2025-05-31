# Exploratory Data Analysis (EDA) in Excel
## Project Facebook Page Performance Comparison
Project นี้เปรียบเทียบ 2 pages ทาง Facebook โดยมีรายละเอียดดังนี้

- import files dramaadd, ejeab, engagement
  - dramaadd ประกอบด้วย columns create_date, create_time, type, message, link, page

ejeab ประกอบด้วย columns create_date, create_time, type, message, link, page

engagement ประกอบด้วย columns id, reactions, comments, shares



โดยเราต้องเอา 3 เพจนี้มา VLOOKUP ให้เป็น Table เดียวกันก่อน เป็น master

จากนั้นเรามาหาวันที่โพส จันทร์-อาทิตย์ โดยใช้ WEEKLY โดยให้วันอาทิตย์เป็น 1

หาชั่วโมง โดยใช้ HOUR

และสุดท้ายในขั้นตอนนี้ ใช้ SEARCH หาใน message ว่ามีคำว่า "555", ถถถ, มอนิ่ง ไหม โดยคำพวกนี้เป็นคำพูดติดปากของ page dramaadd และ ejeab



หลังจากนั้นเราจะมาเปรียบเทียบการโพส ของ 2 pages ว่าใครโพสเยอะกว่ากัน
