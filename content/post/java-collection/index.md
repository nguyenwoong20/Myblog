---
title: "Bài 4 - Java Collections: List, Set, Map"
date: 2025-09-22T10:20:00+07:00
tags: ["java", "collections"]
categories: ["Java"]
series: ["Java cơ bản"]
draft: false
---

Bài này so sánh 3 nhóm chính trong Collections Framework và cách chọn đúng cấu trúc.

## 1) List: Danh sách có thứ tự, cho phép trùng
- Cài đặt phổ biến: `ArrayList` (truy cập nhanh), `LinkedList` (chèn/xóa giữa nhanh hơn).

```java
import java.util.*;

List<String> list = new ArrayList<>();
list.add("A");
list.add("B");
list.add("A"); // trùng OK
System.out.println(list.get(0)); // A
```

## 2) Set: Tập hợp KHÔNG trùng
- `HashSet` (nhanh, không giữ thứ tự), `LinkedHashSet` (giữ thứ tự chèn), `TreeSet` (sắp xếp tự nhiên).

```java
Set<Integer> set = new HashSet<>();
set.add(2);
set.add(1);
set.add(2); // bị bỏ qua
System.out.println(set.contains(1)); // true
```

## 3) Map: Ánh xạ khóa → giá trị
- `HashMap` (nhanh), `LinkedHashMap` (giữ thứ tự chèn), `TreeMap` (sắp xếp theo khóa).

```java
Map<String, Integer> ages = new HashMap<>();
ages.put("An", 20);
ages.put("Bình", 21);
ages.put("An", 22); // ghi đè
System.out.println(ages.get("An")); // 22
```

## 4) Duyệt và thao tác hay dùng
```java
// for-each
for (String x : list) {
    System.out.println(x);
}

// Iterator
Iterator<String> it = list.iterator();
while (it.hasNext()) {
    String x = it.next();
    if (x.equals("B")) it.remove();
}

// Stream API
long countA = list.stream().filter(x -> x.equals("A")).count();
```

## 5) Khi nào dùng cái nào?
- Cần thứ tự và cho phép trùng: List.
- Cần loại bỏ trùng, không quan tâm thứ tự: HashSet.
- Cần tra cứu theo khóa: Map. Nếu cần giữ thứ tự chèn: LinkedHashMap; cần sắp xếp theo khóa: TreeMap.

---

Trước đó: [Bài 3 – Điều kiện & vòng lặp](/p/java-dieu-kien-vong-lap/)

Tiếp theo: [Bài 5 – Hàm & phương thức](/p/java-ham-phuong-thuc/)

