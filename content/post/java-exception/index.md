---
title: "Bài 7 - Java Exception: try-catch, throw, custom exception"
date: 2025-09-22T11:10:00+07:00
tags: ["java", "exception"]
categories: ["Java"]
series: ["Java cơ bản"]
draft: false
---

Phân biệt checked/unchecked, cách xử lý và tạo exception tuỳ biến.

## 1) try-catch-finally
```java
try {
    int x = 10 / 0; // ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("Lỗi chia cho 0: " + e.getMessage());
} finally {
    System.out.println("Luôn chạy dù có lỗi hay không");
}
```

## 2) Checked vs Unchecked
- Checked: bắt buộc khai báo/try-catch (ví dụ: `IOException`, `SQLException`).
- Unchecked (RuntimeException): không bắt buộc (ví dụ: `NullPointerException`).

```java
import java.io.*;

void readFile(String path) throws IOException { // checked → phải throws hoặc try-catch
    try (BufferedReader br = new BufferedReader(new FileReader(path))) {
        System.out.println(br.readLine());
    }
}
```

## 3) throw và throws
- `throw` dùng để ném ra exception tại chỗ.
- `throws` khai báo phương thức có thể ném exception.

```java
public int divide(int a, int b) {
    if (b == 0) throw new IllegalArgumentException("b must not be 0");
    return a / b;
}
```

## 4) Custom exception
```java
class InvalidAgeException extends Exception { // checked
    public InvalidAgeException(String msg) { super(msg); }
}

void register(int age) throws InvalidAgeException {
    if (age < 18) throw new InvalidAgeException("Tuổi phải >= 18");
}
```

## 5) Best practices
- Đừng nuốt lỗi: tránh `catch (Exception e) {}` rỗng.
- Ném exception mô tả rõ ràng, không lạm dụng checked tràn lan.
- Dùng `try-with-resources` để đóng tài nguyên tự động.

---

Trước đó: [Bài 6 – Lớp & đối tượng (OOP)](/p/java-lop-doi-tuong/)

Tiếp theo: [Bài 8 – I/O & xử lý file](/p/java-io-file/)

