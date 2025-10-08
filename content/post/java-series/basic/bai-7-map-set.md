---
title: "Bài 7 - HashMap, Set và HashSet trong Java"
date: 2025-09-22T12:00:00+07:00
categories: ["Java Series", "Java Cơ Bản"]
tags: ["java-basic"]
series: ["Java Basic"]
series_order: 7
draft: false
image: "https://img.youtube.com/vi/TEDZbOH0Y0o/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube TEDZbOH0Y0o >}}

---

## 1) HashMap – Lưu trữ dạng ánh xạ (key/value)
Cấu trúc lưu dữ liệu dạng cặp khóa (key) – giá trị (value), cho phép tra cứu nhanh dựa trên key.

```java
import java.util.HashMap;

HashMap<String, Integer> map = new HashMap<>();
map.put("An", 18);
map.put("Nam", 20);
System.out.println(map.get("An")); // 18
```

## 2) Set và HashSet – Tập hợp không trùng lặp
Set không cho phép phần tử lặp lại, xếp theo thứ tự phụ thuộc vào triển khai (HashSet mất thứ tự).

```java
import java.util.HashSet;

HashSet<String> set = new HashSet<>();
set.add("Java");
set.add("Code Thủ");
set.add("Java"); // không thêm lại!
System.out.println(set.size()); // 2
```

## 3) Khi nào dùng Map, HashSet?
- HashMap dùng khi cần tra cứu theo khóa.
- Set dùng khi muốn loại bỏ dữ liệu trùng.
- Kết hợp lọc dữ liệu với tập hợp lớn.

## 4) Kết luận & cảm nhận
- Nhờ video Code Thủ, mình làm chủ cách chọn cấu trúc lưu trữ phù hợp, tiết kiệm thời gian dựng thuật toán xử lý dữ liệu lớn.

- Lưu ý: Khi thao tác với Map/Set nên thử in ra nhiều trường hợp edge case!

## Tiếp theo: [Bài 8 – Enum và Wrapper Class](/p/java_bai8_enum/)
