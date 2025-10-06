---
title: "Bài 16 - Đệ Quy Trong JavaScript - Recursion"
date: 2025-09-28T16:00:00+07:00
categories: ["JavaScript Series", "JavaScript Cơ Bản"]
tags: ["javascript-basic", "recursion", "algorithm", "problem-solving"]
series: ["JavaScript Basic"]
series_order: 16
draft: false
image: "https://img.youtube.com/vi/LteNqj4DFD8/maxresdefault.jpg"
author: "Code Thu"
weight: 16
summary: "Tìm hiểu Đệ quy - Kỹ thuật giải quyết vấn đề bằng chính nó"
---

## 🎥 Video hướng dẫn chi tiết
**Nguồn:** [Khóa học JavaScript - Kteam](https://www.youtube.com/playlist?list=PL33lvabfss1ywJRoh40x9fmAfgbI1hpVX)
{{< youtube 6yxtJRzx7Qs >}}

---

## 1. Đệ quy là gì?

```javascript
// Đệ quy: function gọi chính nó
// Cần 2 thành phần: Base case + Recursive case

function factorial(n) {
    // Base case - điều kiện dừng
    if (n <= 1) {
        return 1;
    }
    
    // Recursive case - gọi lại chính nó
    return n * factorial(n - 1);
}

console.log(factorial(5)); // 120
// 5! = 5 × 4 × 3 × 2 × 1 = 120
```

## 2. Ví dụ phổ biến

```javascript
// Fibonacci sequence
function fibonacci(n) {
    if (n <= 1) return n;
    return fibonacci(n - 1) + fibonacci(n - 2);
}
console.log(fibonacci(6)); // 8

// Tìm kiếm nhị phân
function binarySearch(arr, target, left = 0, right = arr.length - 1) {
    if (left > right) return -1;
    
    let mid = Math.floor((left + right) / 2);
    
    if (arr[mid] === target) return mid;
    
    if (arr[mid] > target) {
        return binarySearch(arr, target, left, mid - 1);
    } else {
        return binarySearch(arr, target, mid + 1, right);
    }
}

let numbers = [1, 3, 5, 7, 9];
console.log(binarySearch(numbers, 7)); // 3
```

## 3. Xử lý cấu trúc lồng nhau

```javascript
// Tính tổng mảng đa chiều
function sumNestedArray(arr) {
    let sum = 0;
    for (let item of arr) {
        if (Array.isArray(item)) {
            sum += sumNestedArray(item); // Recursive
        } else {
            sum += item; // Base case
        }
    }
    return sum;
}

let nested = [1, [2, 3], [4, [5, 6]], 7];
console.log(sumNestedArray(nested)); // 28

// Flatten mảng
function flattenArray(arr) {
    let result = [];
    for (let item of arr) {
        if (Array.isArray(item)) {
            result = result.concat(flattenArray(item));
        } else {
            result.push(item);
        }
    }
    return result;
}

console.log(flattenArray(nested)); // [1, 2, 3, 4, 5, 6, 7]
```

## 4. Lưu ý quan trọng

```javascript
// ⚠️ Tránh Stack Overflow - luôn có base case
function infiniteRecursion(n) {
    return infiniteRecursion(n); // NGUY HIỂM!
}

// ✅ So sánh với vòng lặp
// Đệ quy - code ngắn gọn nhưng chậm hơn
function factorialRecursive(n) {
    if (n <= 1) return 1;
    return n * factorialRecursive(n - 1);
}

// Vòng lặp - nhanh hơn, ít memory hơn
function factorialIterative(n) {
    let result = 1;
    for (let i = 2; i <= n; i++) {
        result *= i;
    }
    return result;
}
```

## Chốt lại

1. **Đệ quy**: Function gọi chính nó, cần base case và recursive case
2. **Base case**: Điều kiện dừng để tránh vòng lặp vô tận
3. **Ưu điểm**: Code ngắn gọn, phù hợp với cấu trúc lồng nhau
4. **Nhược điểm**: Chậm hơn vòng lặp, tiêu tốn memory, nguy cơ Stack Overflow
5. **Khi dùng**: Cấu trúc đệ quy (tree, nested array), bài toán chia để trị

---

## 🎉 Chúc mừng!

Bạn đã hoàn thành **16 bài** của series **JavaScript Cơ Bản**! 

🚀 **Những gì bạn đã học:**
- Cài đặt NodeJS và chạy JavaScript
- Biến, hằng số và các kiểu dữ liệu
- Toán tử và template literals
- Cấu trúc điều khiển (if-else, switch, loops)
- Functions và higher-order functions
- Đệ quy và các thuật toán cơ bản
