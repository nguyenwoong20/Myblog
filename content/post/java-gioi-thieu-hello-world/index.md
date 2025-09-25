---
title: "Bài 1 - Giới thiệu Java & môi trường lập trình (Hello World)"
date: 2025-09-22T09:00:00+07:00
categories: ["Java", "Java Cơ bản"]
slug: "java_bai1"
series: ["Java cơ bản"]
draft: false
---

## 1) Cài đặt JDK
- Tải JDK (Temurin/Zulu/Oracle), cài đặt theo hệ điều hành.
- Thiết lập `JAVA_HOME` và thêm `%JAVA_HOME%/bin` vào PATH.
```bash
java -version
javac -version
```

## 2) IDE khuyến nghị
- IntelliJ IDEA Community hoặc VS Code (với Java Extension Pack).

## 3) Hello World (dòng lệnh)
```bash
javac Hello.java
java Hello
```

```java
public class Hello {
    public static void main(String[] args) {
        System.out.println("Hello, Java!");
    }
}
```

## 4) Cấu trúc dự án tối giản
- `src/main/java` chứa mã nguồn, `src/test/java` cho kiểm thử.


Tiếp theo: [Bài 2 – Biến & kiểu dữ liệu](/Myblog/p/java_bai2/)


