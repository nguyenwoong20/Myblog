---
title: "Hàm & phương thức trong Java"
date: 2025-09-22T12:20:00+07:00
tags: ["java", "co-ban"]
categories: ["Java"]
series: ["Java cơ bản"]
draft: false
---

## 1) Định nghĩa & gọi phương thức
```java
public class MathUtil {
    public static int add(int a, int b) { // phương thức tĩnh
        return a + b;
    }
}

int s = MathUtil.add(2, 3); // 5
```

## 2) Tham số, trả về, overload
```java
class Printer {
    void print(String s) { System.out.println(s); }
    void print(int n) { System.out.println(n); } // overload theo kiểu tham số
}
```

## 3) Tham trị vs tham chiếu
- Java truyền tham trị; với object, giá trị truyền là tham chiếu (reference) → thay đổi bên trong có thể ảnh hưởng state object.

```java
class Box { int v; }

void set(Box b, int x) { b.v = x; }
Box b = new Box();
set(b, 10);
System.out.println(b.v); // 10
```

## 4) Phạm vi (scope) & `this`
```java
class Counter {
    private int value;
    public Counter(int value) { this.value = value; }
    public void inc() { this.value++; }
}
```

## 5) best practices
- Đặt tên phương thức dạng động từ; ngắn gọn, rõ chức năng.
- Tham số ít và có nghĩa; trả về giá trị thay vì dùng biến toàn cục.

---

Trước đó: [Bài 4 – Collections cơ bản](/p/java-collection/)

Tiếp theo: [Bài 6 – Lớp & đối tượng (OOP)](/p/java-lop-doi-tuong/)

