# 1. What is PostgreSQL?

PostgreSQL একটি ওপেন সোর্স রিলেশনাল ডেটাবেস ম্যানেজমেন্ট সিস্টেম (RDBMS)। এটি SQL (Structured Query Language) ব্যবহার করে কাজ করে এবং ACID (Atomicity, Consistency, Isolation, Durability) বৈশিষ্ট্য মেনে চলে।
### PostgreSQL-এর কিছু বৈশিষ্ট্য:
1. এটি অত্যন্ত শক্তিশালী ও স্থিতিশীল।
2. জটিল কুয়েরি এবং বড় ডেটা হ্যান্ডেল করতে সক্ষম।
3. এতে JSON, XML, এবং কাস্টম ডেটা টাইপ সাপোর্ট করে।

# 2. What is the purpose of a database schema in PostgreSQL?
Schema হলো PostgreSQL-এ একটি **logical structure** বা **নেইমস্পেস (Namespace)** যা ডেটাবেসের বিভিন্ন অবজেক্ট যেমন: **Table, View, Function, Index** ইত্যাদি সংগঠিতভাবে সংরক্ষণ ও ব্যবস্থাপনার জন্য ব্যবহৃত হয়।
### উদাহরণ:
```sql
CREATE TABLE rangers (
    ranger_id SERIAL PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    region VARCHAR(50) NOT NULL
);
```

# 3.Explain the Primary Key and Foreign Key concepts in PostgreSQL.

Primary Key হলো একটি টেবিলের এমন একটি কলাম (বা কলামের সমষ্টি) যা প্রতিটি রেকর্ডকে Uniquely সনাক্ত করে। একটি টেবিলে শুধুমাত্র একটি Primary Key থাকতে পারে। Primary Key-এর মান অবশ্যই ইউনিক ও NULL ছাড়া হতে হবে।
### উদাহরণ:
```sql
CREATE TABLE students (
    student_id SERIAL PRIMARY KEY,
    name VARCHAR(100),
    age INT
);
```
Foreign Key হলো এমন একটি key যা অন্য টেবিলের Primary Key-কে রেফারেন্স করে দুটি টেবিলের মধ্যে সম্পর্ক তৈরি করে ডেটাবেজে রেফারেন্সিয়াল ইন্টেগ্রিটি (Referential Integrity) বজায় রাখে। Foreign Key এর মান অবশ্যই সেই টেবিলের Primary Key-এর সঙ্গে মিল থাকতে হবে

### উদাহরণ:
```sql
CREATE TABLE courses (
    course_id SERIAL PRIMARY KEY,
    course_name VARCHAR(100)
);

CREATE TABLE enrollments (
    enrollment_id SERIAL PRIMARY KEY,
    student_id INT REFERENCES students(student_id),
    course_id INT REFERENCES courses(course_id)
);
```
