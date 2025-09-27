---
title: "Bài 6 - Tính Đóng Gói (Encapsulation) vs Hackers"
date: 2025-09-22T16:00:00+07:00
categories: ["Java Series", "Java Nâng Cao"]
tags: ["java-advanced", "oop"]
series: ["Java Advanced"]
series_order: 6
draft: false
image: "https://img.youtube.com/vi/rTVk4mPyenE/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube rTVk4mPyenE >}}

---

## 1) Tính đóng gói là gì?
Đóng gói (Encapsulation) là việc:
- Gói dữ liệu và phương thức xử lý vào một đơn vị (class)
- Giấu chi tiết triển khai, chỉ công khai những gì cần thiết
- Kiểm soát quyền truy cập vào dữ liệu thông qua các method

## 2) Access Modifiers trong Java

### 2.1. private
- Chỉ truy cập được trong cùng class
```java
public class BankAccount {
    private double balance; // Chỉ truy cập trong class
    
    private void updateBalance(double amount) {
        balance += amount;
    }
}
```

### 2.2. protected
- Truy cập được trong cùng package và các class con
```java
public class Animal {
    protected String name; // Truy cập trong package và class con
}

class Dog extends Animal {
    void setName(String newName) {
        name = newName; // OK vì là class con
    }
}
```

### 2.3. public
- Truy cập được từ mọi nơi
```java
public class User {
    public String username; // Không nên public trực tiếp
    
    public void login() { // Method công khai
        System.out.println("Logging in...");
    }
}
```

### 2.4. default (package-private)
- Truy cập được trong cùng package
```java
class Helper { // Không có modifier = default
    void helperMethod() {
        // Chỉ dùng trong package
    }
}
```

## 3) Getter và Setter
Kiểm soát truy cập thông qua method:

```java
public class Student {
    private String name;
    private int age;
    
    // Getter
    public String getName() {
        return name;
    }
    
    // Setter với validation
    public void setAge(int age) {
        if (age > 0 && age < 150) {
            this.age = age;
        } else {
            throw new IllegalArgumentException("Invalid age");
        }
    }
}
```

## 4) Lợi ích của đóng gói
1. **Bảo mật dữ liệu**
   - Ngăn truy cập trực tiếp
   - Kiểm soát thông qua method

2. **Linh hoạt trong thay đổi**
   ```java
   public class User {
       private String name;
       // Có thể thay đổi cách lưu name mà không ảnh hưởng code bên ngoài
       public String getName() {
           return name.toUpperCase(); // Thêm xử lý
       }
   }
   ```

3. **Dễ bảo trì**
   - Code gọn gàng, có tổ chức
   - Dễ debug và sửa lỗi

## 5) Best Practices

### 5.1. Luôn đóng gói dữ liệu
```java
// Không tốt
public class Bad {
    public String data;
}

// Tốt
public class Good {
    private String data;
    public String getData() {
        return data;
    }
}
```

### 5.2. Validation trong setter
```java
public void setPassword(String password) {
    if (password == null || password.length() < 6) {
        throw new IllegalArgumentException("Invalid password");
    }
    this.password = password;
}
```

### 5.3. Immutable khi có thể
```java
public final class ImmutablePoint {
    private final int x;
    private final int y;
    
    public ImmutablePoint(int x, int y) {
        this.x = x;
        this.y = y;
    }
    
    // Chỉ có getter, không có setter
    public int getX() { return x; }
    public int getY() { return y; }
}
```

## 6) Kết luận & cảm nhận
- Đóng gói là nền tảng cho code an toàn, dễ bảo trì
- Luôn cân nhắc access level phù hợp cho từng thành phần
- Getter/Setter không chỉ là boilerplate code mà còn là cơ chế bảo vệ dữ liệu

## Tiếp theo: [Tính Đa Hình trong Java](/Myblog/p/java_polymorphism/)