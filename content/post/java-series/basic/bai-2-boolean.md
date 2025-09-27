---
title: "Bài 2 - Boolean - Cái Đúng Cái Sai trong JAVA"
date: 2025-09-22T09:30:00+07:00
categories: ["Java Series", "Java Cơ Bản"]
tags: ["java-basic"]
series: ["Java Basic"]
series_order: 2
draft: false
image: "https://img.youtube.com/vi/iscik6EOcMo/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu  
{{< youtube iscik6EOcMo >}}

---

## 1. Kiểu dữ liệu boolean
- **boolean** là kiểu dữ liệu cơ bản trong Java
- Chỉ có 2 giá trị: **true** hoặc **false**
- Dùng để lưu trữ điều kiện đúng/sai

```java
boolean isJavaFun = true;
boolean isBoring = false;
```

## 2. Các phép toán logic
### Phép AND (&&)
- Trả về true khi cả 2 đều true
```java
boolean a = true;
boolean b = true;
System.out.println(a && b); // true

b = false;
System.out.println(a && b); // false
```

### Phép OR (||) 
- Trả về true khi có ít nhất 1 true
```java
boolean x = true;
boolean y = false;
System.out.println(x || y); // true

x = false;
System.out.println(x || y); // false
```

### Phép NOT (!)
- Đảo ngược giá trị boolean
```java
boolean done = true;
System.out.println(!done); // false
```

## 3. So sánh bằng (==) và khác (!=)
```java
int num1 = 5;
int num2 = 5;
boolean isEqual = (num1 == num2); // true
boolean isNotEqual = (num1 != num2); // false
```

## 4. Ứng dụng trong câu điều kiện if
```java
boolean isRaining = true;

if (isRaining) {
    System.out.println("Mang ô đi!");
} else {
    System.out.println("Thời tiết đẹp!");
}
```

## 5. Một số ví dụ thực tế
### Kiểm tra số chẵn lẻ
```java
int number = 10;
boolean isEven = (number % 2 == 0);
System.out.println(number + " là số chẵn: " + isEven);
```

### Kiểm tra tuổi hợp lệ
```java
int age = 20;
boolean isAdult = age >= 18;
System.out.println("Đủ tuổi trưởng thành: " + isAdult);
```

## 6. Lưu ý quan trọng
- Không dùng số 1/0 thay cho true/false
- boolean giúp code dễ đọc, dễ hiểu
- Nên đặt tên biến boolean bắt đầu bằng is/has/can

## Tiếp theo: [Bài 3 – Biến số](/Myblog/p/java_bai3/)