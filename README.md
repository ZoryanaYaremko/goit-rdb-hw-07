# goit-rdb-hw-07
USE hw3;

--  1. Витягнути рік, місяць і день з date
SELECT 
    id,
    date,
    EXTRACT(YEAR FROM date) AS year,
    EXTRACT(MONTH FROM date) AS month,
    EXTRACT(DAY FROM date) AS day
FROM orders;
<img width="1006" height="802" alt="image" src="https://github.com/user-attachments/assets/9b1b2d70-6460-421c-973f-10ab6754f10b" />
-- 2. Додати 1 день до date
SELECT 
    id,
    date,
    DATE_ADD(date, INTERVAL 1 DAY) AS date_plus_one_day
FROM orders;
<img width="656" height="415" alt="image" src="https://github.com/user-attachments/assets/f1cb196d-a120-4c22-becf-b215f528506d" />

-- 3. Перетворити date у timestamp (кількість секунд з 1970-01-01)
SELECT 
    id,
    date,
    UNIX_TIMESTAMP(date) AS timestamp_seconds
FROM orders;
<img width="785" height="395" alt="image" src="https://github.com/user-attachments/assets/d51bd9cc-5ea6-4656-9bf5-8d8498cffab1" />

-- 4. Порахувати кількість рядків у межах дат
SELECT COUNT(*) AS count_in_range
FROM orders
WHERE date BETWEEN '1996-07-10 00:00:00' AND '1996-10-08 00:00:00';
<img width="607" height="259" alt="image" src="https://github.com/user-attachments/assets/fd062313-6dd6-49f2-82e7-d853df2ed4f9" />

-- 5. Створити JSON-об'єкт на основі id і date
SELECT 
    id,
    date,
    JSON_OBJECT('id', id, 'date', date) AS json_data
FROM orders;
<img width="576" height="386" alt="image" src="https://github.com/user-attachments/assets/aef2f487-aea8-4ce1-b0fb-4692fd061026" />


