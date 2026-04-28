# 📘 SQL Basic Notes (Beginner Friendly)

এই নোটগুলোতে SQL এর গুরুত্বপূর্ণ কমান্ডগুলো সহজ ভাষায় উদাহরণসহ দেখানো হয়েছে।

---

## 🔹 SELECT (ডেটা দেখা)

ডেটাবেস থেকে ডেটা বের করতে ব্যবহার হয়।

```sql
SELECT * FROM test LIMIT 0, 5;
```

👉 প্রথম ৫টি row দেখাবে।

---

## 🔹 INSERT INTO (ডেটা যোগ করা)

```sql
INSERT INTO table_name (column1, column2) VALUES (value1, value2);
```

---

## 🔹 UPDATE (ডেটা আপডেট)

```sql
UPDATE students SET number = number + 2;
```

---

## 🔹 DELETE (ডেটা মুছে ফেলা)

```sql
DELETE FROM students WHERE id = 5;
```

```sql
DELETE FROM students ORDER BY id DESC LIMIT 3;
```

---

## 🔹 DROP DATABASE

```sql
DROP DATABASE database_name;
```

---

## 🔹 CREATE TABLE

```sql
CREATE TABLE table_name (...);
```

---

## 🔹 WHERE ... IN

```sql
SELECT * FROM users WHERE age IN (33, 25, 28);
```

---

## 🔹 INNER JOIN

```sql
SELECT username, age, favorite_color 
FROM users 
INNER JOIN profiles 
ON users.user_id = profiles.user_id;
```

---

## 🔹 LEFT JOIN

```sql
SELECT username, age, favorite_color 
FROM users 
LEFT JOIN profiles 
ON users.user_id = profiles.user_id;
```

---

## 🔹 RIGHT JOIN

```sql
SELECT username, age, favorite_color 
FROM users 
RIGHT JOIN profiles 
ON users.user_id = profiles.user_id;
```

---

## 🔹 GROUP BY

```sql
SELECT course_name FROM applicant GROUP BY course_name;
```

---

## 🔹 Alias

```sql
SELECT u.username AS UserName, u.age AS Age, p.favorite_color AS FavColor
FROM users AS u 
LEFT JOIN profiles AS p 
ON u.user_id = p.user_id;
```

---

## 🔹 Aggregate Functions

```sql
SELECT MAX(age) FROM applicant;
SELECT MIN(age) FROM applicant;
SELECT AVG(age) FROM applicant;
SELECT COUNT(age) FROM applicant;
SELECT SUM(age) FROM applicant;
```

---

## 🔹 NOW()

```sql
SELECT NOW();
```

---

## 🔹 CONCAT

```sql
SELECT email, CONCAT(first_name, '--->', age) FROM applicant;
```

---

## 🔹 Subquery

```sql
SELECT MAX(number)
FROM users
WHERE number < (
  SELECT MAX(number) FROM users
);
```

---

## 🔹 Subquery + IN

```sql
SELECT *
FROM users
WHERE id IN (
  SELECT id FROM users WHERE number < 80
);
```

---

## ✅ Tips

- WHERE দিয়ে filter করা যায়  
- JOIN দিয়ে multiple table ব্যবহার করা যায়  
- Alias ব্যবহার করলে query ছোট হয়  
