---
title: "Bài 2 - Sử dụng THIS trong Java để code ngon hơn"
date: 2025-09-22T14:00:00+07:00
categories: ["Java Series", "Java Nâng Cao"]
tags: ["java-advanced"]
series: ["Java Advanced"]
series_order: 2
draft: false
image: "https://img.youtube.com/vi/yvDICGATFDc/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube yvDICGATFDc >}}

---

## 1) Từ khóa this là gì?
`this` đại diện cho đối tượng hiện tại của class, dùng để:
- Phân biệt biến instance và tham số
- Gọi constructor khác
- Trả về instance hiện tại

## 2) Phân biệt biến instance và tham số
```java
public class Student {
    private String name; // biến instance
    
    public Student(String name) { // tham số
        this.name = name; // this.name là biến instance
    }
}
```

## 3) Gọi constructor khác (Constructor Chaining)
```java
public class Student {
    private String name;
    private int age;
    
    public Student() {
        this("No Name", 0); // Gọi constructor có 2 tham số
    }
    
    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }
}
```

## 4) Method Chaining với this
Trả về instance hiện tại để cho phép gọi nhiều method liên tiếp.

```java
public class StringBuilder {
    private String str;
    
    public StringBuilder append(String s) {
        str += s;
        return this; // Trả về đối tượng hiện tại
    }
    
    // Có thể gọi liên tiếp
    StringBuilder sb = new StringBuilder()
        .append("Hello")
        .append(" ")
        .append("World");
}
```

## 5) This trong inner class
Phân biệt đối tượng của outer class và inner class.

```java
public class OuterClass {
    private int x = 10;
    
    class InnerClass {
        private int x = 20;
        
        public void printX() {
            System.out.println("Inner x: " + this.x);      // 20
            System.out.println("Outer x: " + OuterClass.this.x); // 10
        }
    }
}
```

## 6) Khi nào dùng this?
1. Khi có trùng tên biến instance và tham số
2. Muốn gọi constructor khác trong cùng class
3. Cần trả về instance hiện tại (method chaining)
4. Truy cập từ inner class ra outer class

## 7) Kết luận & cảm nhận
- `this` giúp code rõ ràng, tránh nhầm lẫn khi đặt tên
- Method chaining với `this` giúp code ngắn gọn, dễ đọc
- Hiểu về `this` là nền tảng cho nhiều design pattern

## Tiếp theo: [Từ khóa SUPER trong Java](/Myblog/p/java_super/)