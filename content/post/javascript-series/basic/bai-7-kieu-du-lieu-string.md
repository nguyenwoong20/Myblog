---
title: "Bài 7 - Khái Quát Kiểu Dữ Liệu Chuỗi (String) - Xử Lý Văn Bản"
date: 2025-09-28T12:00:00+07:00
categories: ["JavaScript Series", "JavaScript Cơ Bản"]
tags: ["javascript-basic", "string", "text", "datatypes"]
series: ["JavaScript Basic"]
series_order: 7
draft: false
image: "https://img.youtube.com/vi/0ABTCy5FbP4/maxresdefault.jpg"
author: "Code Thu"
weight: 7
summary: "Tìm hiểu chi tiết về kiểu dữ liệu String - Làm chủ việc xử lý văn bản trong JavaScript"
---

## 🎥 Video hướng dẫn chi tiết
**Nguồn:** [Khóa học JavaScript - Kteam](https://www.youtube.com/playlist?list=PL33lvabfss1ywJRoh40x9fmAfgbI1hpVX)
{{< youtube 0ABTCy5FbP4 >}}

---

## 1. String trong JavaScript

**String** (chuỗi) là kiểu dữ liệu để lưu trữ văn bản.

## 2. Cách tạo String

```javascript
// Single quotes
let singleQuote = 'Hello World';

// Double quotes
let doubleQuote = "Hello World";

// Template literals (backticks)
let templateString = `Hello World`;
let multiLine = `Dòng 1
Dòng 2`;

console.log(typeof singleQuote); // "string"
```

## 3. Nối chuỗi

### Cách 1: Toán tử `+`
```javascript
let firstName = "Nguyen";
let lastName = "Van A";
let fullName = firstName + " " + lastName;
console.log(fullName); // "Nguyen Van A"
```

### Cách 2: Template literals (khuyên dùng)
```javascript
let name = "John", age = 30;
let intro = `Tôi là ${name}, ${age} tuổi`;
console.log(intro); // "Tôi là John, 30 tuổi"
```

## 4. Thuộc tính và phương thức String

### Độ dài chuỗi:
```javascript
let text = "JavaScript";
console.log(text.length); // 10
```

### Truy cập ký tự:
```javascript
let word = "Hello";
console.log(word[0]);     // "H"
console.log(word.charAt(0)); // "H"
console.log(word[word.length - 1]); // "o"
```

## 5. Tìm kiếm trong chuỗi

```javascript
let text = "JavaScript Programming";

// indexOf() - Tìm vị trí
console.log(text.indexOf("Script")); // 4
console.log(text.indexOf("Python")); // -1 (không tìm thấy)

// includes() - Kiểm tra có chứa
console.log(text.includes("Java"));  // true
console.log(text.includes("Python")); // false

// startsWith(), endsWith()
console.log(text.startsWith("Java")); // true
console.log(text.endsWith("ing"));    // true
```

## 6. Cắt và thay đổi chuỗi

```javascript
let text = "JavaScript Programming";

// Cắt chuỗi
console.log(text.substring(0, 10));  // "JavaScript"
console.log(text.slice(4, 10));     // "Script"

// Chuyển đổi hoa/thường
console.log(text.toLowerCase());     // "javascript programming"
console.log(text.toUpperCase());     // "JAVASCRIPT PROGRAMMING"

// Loại bỏ khoảng trắng
let messyText = "  Hello World  ";
console.log(messyText.trim());       // "Hello World"

// Thay thế
console.log(text.replace("Java", "Type")); // "TypeScript Programming"
```

## 7. Tách chuỗi

```javascript
let csv = "Apple,Banana,Orange";
let fruits = csv.split(",");
console.log(fruits); // ["Apple", "Banana", "Orange"]

let sentence = "Hello World";
let words = sentence.split(" ");
console.log(words); // ["Hello", "World"]
```

## 8. Bài tập nhỏ

Xử lý thông tin người dùng:
```javascript
function processName(rawName) {
    return rawName
        .trim()
        .split(" ")
        .map(word => word.charAt(0).toUpperCase() + word.slice(1).toLowerCase())
        .join(" ");
}

console.log(processName("  jOhN dOe  ")); // "John Doe"
```

## Chốt lại:

Bài 7 giúp bạn hiểu về kiểu dữ liệu String, cách tạo chuỗi (single quotes, double quotes, template literals), nối chuỗi, các phương thức quan trọng như length, charAt, indexOf, includes, substring, split, và cách xử lý chuỗi trong thực tế.

---

### 📚 Bài tiếp theo
👉 [**Bài 8: Template Literals, Number-String**](../bai-8-template-literals/) - Tìm hiểu sâu về template literals và chuyển đổi giữa Number-String!
