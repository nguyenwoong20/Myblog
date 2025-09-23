---
title: "Bài 2 - Java cơ bản: Biến, Kiểu dữ liệu, Toán tử"
date: 2025-09-22T10:00:00+07:00
tags: ["java", "co-ban"]
categories: ["Java"]
series: ["Java cơ bản"]
draft: false
---

Trong bài này, bạn sẽ nắm vững 3 nền tảng: biến (variables), kiểu dữ liệu (types) và toán tử (operators) trong Java.

## 1) Biến (Variables)
- Biến phải KHAI BÁO KIỂU ngay từ đầu.
- Tên biến dùng `camelCase`, không bắt đầu bằng số, tránh ký tự đặc biệt.

```java
public class VariablesDemo {
    public static void main(String[] args) {
        int age = 20;               // số nguyên
        double price = 19.99;       // số thực
        boolean active = true;      // true/false
        char grade = 'A';           // ký tự đơn
        String name = "An";        // chuỗi (là một lớp)

        // khai báo rồi gán sau
        int count;
        count = 5;
        System.out.println(name + " - age: " + age + ", count: " + count);
    }
}
```

## 2) Kiểu dữ liệu (Types)
- Nguyên thủy (primitive): `byte, short, int, long, float, double, char, boolean`.
- Tham chiếu (reference): lớp (`String`, `ArrayList`…), mảng, interface…
- Dùng hậu tố `L` cho `long`, `f` cho `float`.

```java
long population = 8_045_311_000L; // dấu gạch dưới giúp đọc số dễ hơn
float ratio = 0.75f;
double pi = 3.1415926535;
String s = "Hello";
int[] arr = {1, 2, 3};
```

## 3) Ép kiểu (Casting)
- Thu hẹp (narrowing) cần ép kiểu tường minh; mở rộng (widening) thường tự động.

```java
double d = 9.8;
int i = (int) d;     // 9 (mất phần thập phân)
long l = i;          // widening OK
```

## 4) Toán tử (Operators)
- Số học: `+ - * / %`
- Gán/phối hợp: `=, +=, -=, *=, /=, %=`
- So sánh: `==, !=, <, <=, >, >=`
- Logic: `&&, ||, !`
- Tăng/giảm: `++ --`

```java
int a = 7, b = 3;
System.out.println(a / b);  // 2 (chia nguyên)
System.out.println(a % b);  // 1

double x = 7.0;
System.out.println(x / b);  // 2.333...

boolean ok = (a > b) && (b > 0);
```

## 5) Chuỗi và nối chuỗi
```java
String first = "Java";
String second = " cơ bản";
String result = first + second; // nối bằng +
System.out.println(result);
```

## 6) Nhập xuất cơ bản (Scanner)
```java
import java.util.Scanner;

public class IOExample {
    public static void main(String[] args) {
        Scanner sc = new Scanner(System.in);
        System.out.print("Nhập tên: ");
        String name = sc.nextLine();
        System.out.println("Xin chào, " + name + "!");
        sc.close();
    }
}
```

## Tổng kết
- Ghi nhớ sự khác nhau giữa số nguyên và số thực khi chia.
- Phân biệt primitive vs reference.
- Dùng ép kiểu cẩn thận để tránh mất dữ liệu.

---

Trước đó: [Bài 1 – Giới thiệu & Hello World](/p/java-gioi-thieu-hello-world/)

Tiếp theo: [Bài 3 – Điều kiện & vòng lặp](/p/java-dieu-kien-vong-lap/)

