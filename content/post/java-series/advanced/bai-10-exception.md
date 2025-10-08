---
title: "Bài 10 - Exception Trong Java - Xử Lý Ngoại Lệ Chuyên Nghiệp"
date: 2025-09-22T19:00:00+07:00
categories: ["Java Series", "Java Nâng Cao"]
tags: ["java-advanced"]
series: ["Java Advanced"]
series_order: 10
draft: false
image: "https://img.youtube.com/vi/EVoMK9Yo0fY/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube EVoMK9Yo0fY >}}

---

## 1) Exception là gì?
- Là sự kiện xảy ra trong quá trình thực thi chương trình làm gián đoạn luồng bình thường
- VD: NullPointerException, ArrayIndexOutOfBoundsException, FileNotFoundException...

## 2) Try-catch cơ bản
```java
try {
    int result = 10 / 0; // Ném ArithmeticException
} catch (ArithmeticException e) {
    System.out.println("Không thể chia cho 0");
} finally {
    System.out.println("Luôn được thực thi");
}
```

## 3) Multiple catch blocks
```java
try {
    int[] arr = new int[5];
    arr[10] = 50; // ArrayIndexOutOfBoundsException
    int num = Integer.parseInt("abc"); // NumberFormatException
} catch (ArrayIndexOutOfBoundsException e) {
    System.out.println("Lỗi truy cập mảng");
} catch (NumberFormatException e) {
    System.out.println("Lỗi chuyển đổi số");
} catch (Exception e) { // Bắt tất cả exception khác
    System.out.println("Lỗi: " + e.getMessage());
}
```

## 4) Throw và Throws
```java
public class AgeValidator {
    public static void validateAge(int age) throws IllegalArgumentException {
        if (age < 0) {
            throw new IllegalArgumentException("Tuổi không được âm");
        }
        if (age > 150) {
            throw new IllegalArgumentException("Tuổi không hợp lệ");
        }
    }
    
    public static void main(String[] args) {
        try {
            validateAge(-5);
        } catch (IllegalArgumentException e) {
            System.out.println("Lỗi: " + e.getMessage());
        }
    }
}
```

## 5) Custom Exception
```java
class InsufficientBalanceException extends Exception {
    public InsufficientBalanceException(String message) {
        super(message);
    }
}

class BankAccount {
    private double balance;
    
    public void withdraw(double amount) throws InsufficientBalanceException {
        if (amount > balance) {
            throw new InsufficientBalanceException("Số dư không đủ");
        }
        balance -= amount;
    }
}
```

## 6) Best Practices
1. Luôn xử lý các exception cụ thể trước Exception chung
2. Đóng tài nguyên trong finally hoặc dùng try-with-resources
3. Log exception đầy đủ trong production
4. Tránh catch exception mà không xử lý
5. Tạo custom exception có ý nghĩa

## Tiếp theo: [Collection trong Java](/p/java_collection/)
