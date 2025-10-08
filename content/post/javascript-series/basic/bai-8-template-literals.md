---
title: "Bài 8 - Template Literals, Number-String - Công Cụ Mạnh Mẽ ES6"
date: 2025-09-28T12:30:00+07:00
categories: ["JavaScript Series", "JavaScript Cơ Bản"]
tags: ["javascript-basic", "template-literals", "es6", "string-number"]
series: ["JavaScript Basic"]
series_order: 8
draft: false
image: "https://img.youtube.com/vi/hiFBsPtFgOg/maxresdefault.jpg"
author: "Code Thu"
weight: 8
summary: "Khám phá Template Literals ES6 và cách chuyển đổi giữa Number-String một cách hiệu quả"
---

## 🎥 Video hướng dẫn chi tiết
**Nguồn:** [Khóa học JavaScript - Kteam](https://www.youtube.com/playlist?list=PL33lvabfss1ywJRoh40x9fmAfgbI1hpVX)
{{< youtube hiFBsPtFgOg >}}

---

## 1. Template Literals - Cách mới tạo String

**Template Literals** sử dụng backticks (`` ` ``) thay vì quotes:

### Cách cũ (ES5):
```javascript
let name = "John", age = 25;
let oldWay = "Xin chào, tôi là " + name + ", " + age + " tuổi.";
```

### Cách mới (ES6):
```javascript
let name = "John", age = 25;
let newWay = `Xin chào, tôi là ${name}, ${age} tuổi.`;
```

## 2. String Interpolation với ${}

```javascript
let product = "iPhone", price = 25000000, quantity = 2;

let invoice = `Sản phẩm: ${product}
Giá: ${price.toLocaleString('vi-VN')} VND
Số lượng: ${quantity}
Thành tiền: ${(price * quantity).toLocaleString('vi-VN')} VND`;

console.log(invoice);
```

### Gọi hàm trong template:
```javascript
function getDiscount(price) {
    return price > 1000000 ? 10 : 5;
}

let message = `Giảm giá: ${getDiscount(25000000)}%
Thời gian: ${new Date().toLocaleString('vi-VN')}`;
```

## 3. Multi-line Strings

```javascript
let userName = "John Doe", userEmail = "john@example.com";

let htmlTemplate = `
<div class="user-card">
    <h1>Welcome, ${userName}!</h1>
    <p>Email: ${userEmail}</p>
    <button onclick="logout()">Logout</button>
</div>`;

console.log(htmlTemplate);
```

## 4. Chuyển đổi Number ↔ String

### String to Number:
```javascript
let str1 = "123", str2 = "45.67", str3 = "123abc";

// Number() - Nghiêm ngặt
console.log(Number(str1));    // 123
console.log(Number(str3));    // NaN

// parseInt(), parseFloat() - Lấy số từ đầu
console.log(parseInt(str3));     // 123 (bỏ phần chữ)
console.log(parseFloat(str2));   // 45.67

// Unary operator + - Ngắn gọn
console.log(+str1);             // 123
```

### Number to String:
```javascript
let num = 123.456;

console.log(num.toString());     // "123.456"
console.log(String(num));        // "123.456"
console.log(`${num}`);           // "123.456" (template literal)
console.log(num + "");           // "123.456" (nối chuỗi rỗng)
```

### Formatting Numbers:
```javascript
let number = 1234567.89;

console.log(number.toFixed(2));      // "1234567.89"
console.log(number.toLocaleString('vi-VN')); // "1.234.567,89"
```

## 5. Bài tập nhỏ

Tạo template HTML:
```javascript
function createUserCard(user) {
    return `
<div class="user-card">
    <h3>${user.name}</h3>
    <p>Email: ${user.email}</p>
    <p>Role: ${user.role}</p>
</div>`;
}

let user = { name: "John", email: "john@email.com", role: "Admin" };
console.log(createUserCard(user));
```

Format số tiền:
```javascript
function formatMoney(amount) {
    return `${amount.toLocaleString('vi-VN')} VND`;
}

console.log(formatMoney(1234567)); // "1.234.567 VND"
```

## Chốt lại:

Bài 8 giúp bạn hiểu Template Literals với backticks và `${}` để nhúng biểu thức, tạo multi-line strings, chuyển đổi giữa Number và String bằng Number(), parseInt(), parseFloat(), toString(), và cách format số với toFixed(), toLocaleString().

---

### 📚 Bài tiếp theo
👉 [**Bài 9: Kiểu dữ liệu Boolean**](../bai-9-kieu-du-lieu-boolean/) - Tìm hiểu về logic đúng/sai và các phép toán Boolean!
