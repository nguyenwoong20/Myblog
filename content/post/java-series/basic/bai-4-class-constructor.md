---
title: "Bài 4 - Lớp (Class) và Constructor trong Java"
date: 2025-09-22T10:30:00+07:00
categories: ["Java Series", "Java Cơ Bản"]
tags: ["java-basic"]
series: ["Java Basic"]
series_order: 4
draft: false
image: "https://img.youtube.com/vi/n33H9XSXRxc/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube n33H9XSXRxc >}}

---

## 1) Khái niệm Class trong Java
Class là bản thiết kế cho đối tượng – mô tả thuộc tính (biến) và hành động (phương thức) chung cho một loại sự vật.

Khi tạo object (đối tượng) từ class, ta sử dụng bản thiết kế này để sinh ra thực thể thật dùng trong chương trình.

Ví dụ:

```java
class Student {
    String name;
    int age;
    void introduce() {
        System.out.println(name + " - " + age);
    }
}

Student s = new Student();
s.name = "An";
s.age = 20;
s.introduce(); // In: An - 20
```

## 2) Constructor (Hàm tạo) là gì?
Constructor là một phương thức đặc biệt dùng để khởi tạo đối tượng từ class.

Tên constructor trùng tên class, không có kiểu trả về, gọi tự động khi dùng từ khóa new.

Ví dụ:

```java
public class Student {
    String name;
    public Student(String studentName) {
        name = studentName;
    }
}

Student sv = new Student("Nam");
System.out.println(sv.name); // Nam
```

## 3) Default Constructor & Overloading
Nếu bạn không tạo constructor, Java tự thêm constructor mặc định (không nhận tham số).

Có thể tạo nhiều constructor với tham số khác nhau (constructor overloading).

Ví dụ:

```java
public class Student {
    String name;
    int age;
    public Student() {
        name = "No Name";
        age = 0;
    }
    public Student(String n, int a) {
        name = n;
        age = a;
    }
}
Student s1 = new Student();
Student s2 = new Student("Long", 22);
```

## 4) Khái niệm THIS
Từ khóa this đại diện cho đối tượng hiện tại, dùng để phân biệt biến thành phần và tham số trong constructor hoặc phương thức.

```java
public Student(String name) {
    this.name = name;
}
```

## 5) Kết luận & cảm nhận
- Xem video của Code Thủ giúp mình hiểu gốc rễ về cách tạo/làm việc với class, sử dụng constructor linh hoạt và phân biệt rõ giữa biến thành phần - biến cục bộ.

- Class, constructor và kỹ năng dùng this chuẩn xác là chìa khoá lập trình OOP Java hiệu quả.

## Tiếp theo: [Bài 5 – Điều kiện & vòng lặp](/Myblog/p/java_bai5_control/)