## 1. What is PostgreSQL?

PostgreSQL একটি ওপেন সোর্স রিলেশনাল ডেটাবেস ম্যানেজমেন্ট সিস্টেম (RDBMS)। এটি SQL (Structured Query Language) ব্যবহার করে কাজ করে এবং ACID (Atomicity, Consistency, Isolation, Durability) বৈশিষ্ট্য মেনে চলে।
### PostgreSQL-এর কিছু বৈশিষ্ট্য:
1. এটি অত্যন্ত শক্তিশালী ও স্থিতিশীল।
2. জটিল কুয়েরি এবং বড় ডেটা হ্যান্ডেল করতে সক্ষম।
3. এতে JSON, XML, এবং কাস্টম ডেটা টাইপ সাপোর্ট করে।

## 2. What is the purpose of a database schema in PostgreSQL?
Schema হলো PostgreSQL-এ একটি **logical structure** বা **নেইমস্পেস (Namespace)** যা ডেটাবেসের বিভিন্ন অবজেক্ট যেমন: **Table, View, Function, Index** ইত্যাদি সংগঠিতভাবে সংরক্ষণ ও ব্যবস্থাপনার জন্য ব্যবহৃত হয়।
## উদাহরণ:
```sql
CREATE TABLE rangers (
    ranger_id SERIAL PRIMARY KEY,
    name VARCHAR(50) NOT NULL,
    region VARCHAR(50) NOT NULL
);
