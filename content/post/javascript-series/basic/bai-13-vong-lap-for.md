---
title: "Bài 13 - Vòng Lặp For - Lặp Với Số Lần Xác Định"
date: 2025-09-28T15:00:00+07:00
categories: ["JavaScript Series", "JavaScript Cơ Bản"]
tags: ["javascript-basic", "for-loop", "loops", "iteration"]
series: ["JavaScript Basic"]
series_order: 13
draft: false
image: "https://img.youtube.com/vi/WUFb_huPvtI/maxresdefault.jpg"
author: "Code Thu"
weight: 13
summary: "Tìm hiểu vòng lặp for và các biến thể - Công cụ mạnh mẽ để lặp qua dữ liệu"
---

## 🎥 Video hướng dẫn chi tiết
**Nguồn:** [Khóa học JavaScript - Kteam](https://www.youtube.com/playlist?list=PL33lvabfss1ywJRoh40x9fmAfgbI1hpVX)
{{< youtube WUFb_huPvtI >}}

---

## 1. Vòng lặp for cơ bản

```javascript
// Cú pháp: for (initialization; condition; increment)
for (let i = 1; i <= 5; i++) {
    console.log(i);
}
// Kết quả: 1, 2, 3, 4, 5

// Lặp qua mảng
let fruits = ["Apple", "Banana", "Orange"];
for (let i = 0; i < fruits.length; i++) {
    console.log(fruits[i]);
}
```

## 2. Các biến thể

```javascript
// for...of - Lặp qua giá trị
let colors = ["red", "green", "blue"];
for (let color of colors) {
    console.log(color);
}

// for...in - Lặp qua key
let person = { name: "John", age: 30 };
for (let key in person) {
    console.log(key + ": " + person[key]);
}

// Vòng lặp lồng nhau
for (let i = 1; i <= 3; i++) {
    for (let j = 1; j <= 3; j++) {
        console.log(i + " x " + j + " = " + i*j);
    }
}
```

## 3. Ví dụ thực tế

```javascript
// Tính tổng các số trong mảng
let numbers = [1, 2, 3, 4, 5];
let sum = 0;
for (let i = 0; i < numbers.length; i++) {
    sum += numbers[i];
}
console.log("Tổng:", sum); // 15

// Tìm số lớn nhất
let scores = [85, 92, 78, 96, 88];
let max = scores[0];
for (let i = 1; i < scores.length; i++) {
    if (scores[i] > max) {
        max = scores[i];
    }
}
console.log("Điểm cao nhất:", max); // 96

// Đếm số chẵn/lẻ
let evenCount = 0, oddCount = 0;
for (let num of numbers) {
    if (num % 2 === 0) {
        evenCount++;
    } else {
        oddCount++;
    }
}
console.log("Chẵn:", evenCount, "Lẻ:", oddCount);
```

## Chốt lại

1. **for loop**: `for (init; condition; increment)` - biết trước số lần lặp
2. **for...of**: Lặp qua giá trị của arrays, strings
3. **for...in**: Lặp qua keys/properties của objects
4. **Nested loops**: Vòng lặp lồng nhau cho ma trận 2D
5. **Best practices**: Dùng `for...of` cho arrays, `for...in` cho objects

---

### 📚 Bài tiếp theo
👉 [**Bài 14: Function trong JavaScript**](../bai-14-function-javascript/) - Tìm hiểu về functions - Building blocks của JavaScript!