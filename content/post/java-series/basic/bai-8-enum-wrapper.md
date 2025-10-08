---
title: "Bài 8 - Enum và Wrapper Class trong Java"
date: 2025-09-22T12:30:00+07:00
categories: ["Java Series", "Java Cơ Bản"]
tags: ["java-basic"]
series: ["Java Basic"]
series_order: 8
draft: false
image: "https://img.youtube.com/vi/vKvBz238wfg/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube vKvBz238wfg >}}

---

## 1) Enum là gì?
Enum là kiểu dữ liệu liệt kê, chứa các hằng số cố định, thường dùng đại diện nhóm giá trị ràng buộc.

```java
enum Day { MON, TUE, WED, THU, FRI, SAT, SUN }
Day today = Day.SAT;
System.out.println(today); // SAT
```

Duyệt enum:
```java
for (Day d : Day.values()) {
    System.out.println(d);
}
```

## 2) Wrapper Class
Lớp bao (Wrapper) như Integer, Double, Boolean... giúp dùng các kiểu dữ liệu nguyên thủy như đối tượng.

```java
int x = 5;
Integer xx = x;
System.out.println(xx.compareTo(8)); // -1
```

Dùng Wrapper khi làm việc với collections/ArrayList (chỉ nhận object).

## 3) Khi nào dùng Enum, Wrapper?
- Enum: dùng cho nhóm giá trị giới hạn (trạng thái, ngày trong tuần, loại đơn hàng...).
- Wrapper: cần tính năng object với giá trị số/nguyên thủy, truyền qua API/library.

## 4) Kết luận & cảm nhận
- Video Code Thủ giúp mình hiểu, tận dụng enum cho code rõ ràng, giảm bug vì giá trị sai lệch.

- Wrapper class cực kỳ hữu ích khi thao tác collection, sử dụng phương thức tiện ích của lớp đối tượng.

## Tiếp theo: [Bài 9 – Exception Handling](/p/java_bai9/)
