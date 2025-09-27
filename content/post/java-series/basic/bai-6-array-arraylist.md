---
title: "Bài 6 - Mảng (Array) và ArrayList trong Java"
date: 2025-09-22T11:30:00+07:00
categories: ["Java Series", "Java Cơ Bản"]
tags: ["java-basic"]
series: ["Java Basic"]
series_order: 6
draft: false
image: "https://img.youtube.com/vi/uzZ8rwgkPqU/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube uzZ8rwgkPqU >}}

---

## 1) Mảng (Array) là gì?
Mảng lưu nhiều giá trị cùng kiểu, truy xuất bằng chỉ số.

Số phần tử mảng được cố định khi khởi tạo.

```java
int[] nums = new int[3];
nums[0] = 10;
nums[1] = 20;
nums[2] = 30;
System.out.println(nums[1]); // 20
```

Khởi tạo nhanh:

```java
String[] names = {"An", "Bình", "Chi"};
```

## 2) Duyệt mảng
```java
for (int i = 0; i < nums.length; i++) {
    System.out.println(nums[i]);
}
```

## 3) Giới thiệu ArrayList
Kết cấu động (co giãn tự động, có thể thêm/xóa phần tử linh hoạt).

```java
import java.util.ArrayList;

ArrayList<String> list = new ArrayList<>();
list.add("Java");
list.add("Code Thủ");
System.out.println(list.get(1)); // Code Thủ
```

Duyệt ArrayList:

```java
for (String item : list) {
    System.out.println(item);
}
```

## 4) So sánh array vs ArrayList

| Tiêu chí | Array | ArrayList |
|----------|--------|------------|
| Kích thước | Cố định | Linh hoạt |
| Kiểu dữ liệu | Phải xác định cụ thể | Có thể dùng object |
| Tăng/giảm | Không | Dùng add/remove |

## 5) Kết luận & cảm nhận
- Video Code Thủ giúp mình biết chọn mảng khi dữ liệu cố định trước, dùng ArrayList khi cần mở rộng.

- Biết kết hợp duyệt mảng, thao tác cơ bản sẽ cực kỳ thuận lợi cho các bài toán lớn hơn.

## Tiếp theo: [Bài 7 – HashMap & Set](/Myblog/p/java_bai7_mapset/)