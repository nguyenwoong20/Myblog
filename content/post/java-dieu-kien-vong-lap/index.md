---
title: "Bài 3 - Câu điều kiện & vòng lặp trong Java"
date: 2025-09-22T12:10:00+07:00
categories: ["Java", "Java Cơ bản"]
slug: "java_bai3"
series: ["Java cơ bản"]
draft: false
---

## 1) if / else if / else
```java
int n = 10;
if (n > 0) {
    System.out.println("dương");
} else if (n < 0) {
    System.out.println("âm");
} else {
    System.out.println("0");
}
```

## 2) switch (Java 14+)
```java
String role = "admin";
int level = switch (role) {
    case "admin" -> 3;
    case "editor" -> 2;
    case "viewer" -> 1;
    default -> 0;
};
```

## 3) for, while, do-while
```java
for (int i = 0; i < 3; i++) System.out.println(i);

int j = 0;
while (j < 3) { System.out.println(j); j++; }

int k = 0;
do { System.out.println(k); k++; } while (k < 3);
```

## 4) break, continue, label
```java
outer:
for (int i = 0; i < 3; i++) {
    for (int m = 0; m < 3; m++) {
        if (m == 1) continue; // bỏ qua 1
        if (i == 2) break outer; // thoát hẳn 2 vòng
        System.out.printf("(%d,%d) ", i, m);
    }
}
```

## 5) Bài tập nhỏ
- In số lẻ từ 1..100.
- Tính tổng các số chia hết cho 3 từ 1..n (n nhập từ bàn phím).

---

Trước đó: [Bài 2 – Biến & kiểu dữ liệu](/Myblog/p/java_bai2/)

Tiếp theo: [Bài 4 – Mảng & Collections cơ bản](/Myblog/p/java_bai4/)

