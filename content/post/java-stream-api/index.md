---
title: "Bài 9 - Java Stream API: map, filter, reduce"
date: 2025-09-22T11:00:00+07:00
tags: ["java", "stream"]
categories: ["Java"]
series: ["Java cơ bản"]
draft: false
---

Làm sạch, biến đổi và tổng hợp dữ liệu với Stream API.

## 1) Khởi tạo Stream
```java
import java.util.*;
import java.util.stream.*;

List<Integer> nums = Arrays.asList(1, 2, 3, 4, 5);
Stream<Integer> s = nums.stream();
```

## 2) map, filter, collect
```java
List<Integer> squaresOfEven = nums.stream()
        .filter(n -> n % 2 == 0)   // giữ số chẵn
        .map(n -> n * n)           // bình phương
        .collect(Collectors.toList());
```

## 3) reduce (tổng, tích, max, min)
```java
int sum = nums.stream().reduce(0, Integer::sum);       // 15
int product = nums.stream().reduce(1, (a, b) -> a * b); // 120
int max = nums.stream().max(Integer::compare).orElse(0);
```

## 4) distinct, sorted, limit, skip
```java
List<Integer> result = Stream.of(5, 2, 2, 3, 1, 4)
        .distinct()
        .sorted()
        .skip(1)
        .limit(3)
        .collect(Collectors.toList()); // [2,3,4] → sau khi skip 1 là [3,4,5], limit 3
```

## 5) mapToInt / average
```java
double avg = nums.stream().mapToInt(Integer::intValue).average().orElse(0);
```

## 6) So sánh với vòng lặp
```java
int sumLoop = 0;
for (int n : nums) sumLoop += n;

int sumStream = nums.stream().mapToInt(Integer::intValue).sum();
```

## 7) Lưu ý hiệu năng
- Stream phù hợp thao tác khai báo, ngắn gọn; vòng lặp truyền thống vẫn tốt cho hotspot đơn giản.
- Tránh tạo stream mới trong vòng lặp lớn.

---

Trước đó: [Bài 8 – I/O & xử lý file](/p/java-io-file/)

