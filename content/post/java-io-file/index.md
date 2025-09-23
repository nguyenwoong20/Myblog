---
title: "Đầu vào/đầu ra & xử lý file trong Java"
date: 2025-09-22T12:30:00+07:00
tags: ["java", "io"]
categories: ["Java"]
series: ["Java cơ bản"]
draft: false
---

## 1) Đọc file (BufferedReader)
```java
import java.io.*;

try (BufferedReader br = new BufferedReader(new FileReader("input.txt"))) {
    String line;
    while ((line = br.readLine()) != null) {
        System.out.println(line);
    }
} catch (IOException e) {
    e.printStackTrace();
}
```

## 2) Ghi file (BufferedWriter)
```java
import java.io.*;

try (BufferedWriter bw = new BufferedWriter(new FileWriter("output.txt"))) {
    bw.write("Xin chào\n");
    bw.write("Java IO\n");
} catch (IOException e) {
    e.printStackTrace();
}
```

## 3) NIO Files API
```java
import java.nio.file.*;
import java.io.IOException;

try {
    Path p = Paths.get("data.txt");
    Files.writeString(p, "Hello NIO\n");
    String content = Files.readString(p);
    System.out.println(content);
} catch (IOException e) {
    e.printStackTrace();
}
```

## 4) Kết hợp với Stream API
```java
import java.nio.file.*;
import java.io.IOException;

try {
    long lines = Files.lines(Paths.get("data.txt")).count();
    System.out.println("Số dòng: " + lines);
} catch (IOException e) { e.printStackTrace(); }
```

## 5) Lưu ý
- Dùng `try-with-resources` để đóng tài nguyên tự động.
- Xử lý `IOException` đúng cách; tránh nuốt lỗi.

---

Trước đó: [Bài 8 – Exception](/p/java-exception/)

Xem thêm: [Bài 9 – Stream API](/p/java-stream-api/)

