---
title: "Bài 9 - String Bất Biến (Immutable) trong Java"
date: 2025-09-22T13:00:00+07:00
categories: ["Java Series", "Java Cơ Bản"]
tags: ["java-basic"]
series: ["Java Basic"]
series_order: 9
draft: false
image: "https://img.youtube.com/vi/AQzJAA994OE/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube AQzJAA994OE >}}

---

## 1) String là immutable - bất biến
String trong Java là bất biến (immutable) - nghĩa là không thể thay đổi sau khi tạo.

```java
String s1 = "Hello";
s1.concat(" World"); // Tạo string mới nhưng không gán lại
System.out.println(s1); // Vẫn in "Hello"

// Phải gán kết quả vào biến mới
String s2 = s1.concat(" World");
System.out.println(s2); // In "Hello World"
```

## 2) String Pool
Java sử dụng String Pool để tối ưu bộ nhớ, tái sử dụng string giống nhau.

```java
String str1 = "Java";
String str2 = "Java"; // Trỏ cùng về 1 vị trí trong pool
System.out.println(str1 == str2); // true

String str3 = new String("Java"); // Tạo đối tượng mới
System.out.println(str1 == str3); // false
```

## 3) So sánh String đúng cách
Do cơ chế String Pool, không nên dùng == để so sánh String.

```java
String a = "Code";
String b = new String("Code");

System.out.println(a == b);         // false
System.out.println(a.equals(b));    // true - cách đúng
```

## 4) Hiệu suất với String
Khi cần nối nhiều String, dùng StringBuilder thay vì toán tử +.

```java
// Không hiệu quả
String result = "";
for (int i = 0; i < 1000; i++) {
    result += i; // Tạo nhiều đối tượng String mới
}

// Hiệu quả hơn
StringBuilder sb = new StringBuilder();
for (int i = 0; i < 1000; i++) {
    sb.append(i); // Thay đổi trực tiếp nội dung
}
String result = sb.toString();
```

## 5) Kết luận & cảm nhận
- String bất biến giúp code an toàn hơn, tránh thay đổi nội dung không mong muốn
- Hiểu về String Pool giúp tối ưu bộ nhớ và viết code so sánh chính xác
- StringBuilder là giải pháp hiệu quả khi cần thao tác String nhiều lần

## Tiếp theo: [Constructor nâng cao trong Java](/Myblog/p/java_constructor_advanced/)