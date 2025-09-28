---
title: "Bài 11 - Câu Lệnh Điều Kiện if-else, switch-case - Điều Khiển Luồng"
date: 2025-09-28T14:00:00+07:00
categories: ["JavaScript Series", "JavaScript Cơ Bản"]
tags: ["javascript-basic", "if-else", "switch-case", "control-flow"]
series: ["JavaScript Basic"]
series_order: 11
draft: false
image: "https://img.youtube.com/vi/g6AVmwqtnyw/maxresdefault.jpg"
author: "Code Thu"
weight: 11
summary: "Học cách sử dụng if-else và switch-case để điều khiển luồng chương trình trong JavaScript"
---

## 🎥 Video hướng dẫn chi tiết
**Nguồn:** [Khóa học JavaScript - Kteam](https://www.youtube.com/playlist?list=PL33lvabfss1ywJRoh40x9fmAfgbI1hpVX)
{{< youtube g6AVmwqtnyw >}}

---

## 1. Câu lệnh if

```javascript
let age = 18;

// If đơn giản
if (age >= 18) {
    console.log("Đủ tuổi!");
}

// If với điều kiện phức tạp
let hasLicense = true;
if (age >= 18 && hasLicense) {
    console.log("Có thể lái xe!");
}
```

## 2. if-else statement

```javascript
let score = 75;

if (score >= 90) {
    console.log("Xuất sắc - A");
} else if (score >= 80) {
    console.log("Giỏi - B");
} else if (score >= 70) {
    console.log("Khá - C");
} else if (score >= 60) {
    console.log("Trung bình - D");
} else {
    console.log("Yếu - F");
}

// Phân loại thời gian
let time = 14;
if (time < 6) {
    console.log("Đêm khuya");
} else if (time < 12) {
    console.log("Buổi sáng");
} else if (time < 18) {
    console.log("Buổi chiều");
} else {
    console.log("Buổi tối");
}
```

## 3. switch-case statement

```javascript
let dayOfWeek = 3;

switch (dayOfWeek) {
    case 1:
        console.log("Thứ hai");
        break;
    case 2:
        console.log("Thứ ba");
        break;
    case 3:
        console.log("Thứ tư");
        break;
    default:
        console.log("Ngày khác");
}

// Fall-through behavior
let month = 12;
switch (month) {
    case 12:
    case 1:
    case 2:
        console.log("Mùa đông");
        break;
    case 3:
    case 4:
    case 5:
        console.log("Mùa xuân");
        break;
    default:
        console.log("Mùa khác");
}

// Switch với string
let userRole = "admin";
switch (userRole) {
    case "admin":
        console.log("Quyền: Quản trị hệ thống");
        break;
    case "editor":
        console.log("Quyền: Biên tập nội dung");
        break;
    default:
        console.log("Quyền: Không xác định");
}
```

## 4. Ternary Operator

```javascript
let age = 20;

// Cú pháp: condition ? valueIfTrue : valueIfFalse
let message = age >= 18 ? "Người lớn" : "Trẻ em";
console.log(message); // "Người lớn"

// Nested ternary
let score = 85;
let grade = score >= 90 ? "A" : 
            score >= 80 ? "B" : 
            score >= 70 ? "C" : "D";

// Trong template literals
let user = { name: "John", isOnline: true };
let status = `${user.name} ${user.isOnline ? 'online' : 'offline'}`;
console.log(status); // "John online"
```

## Chốt lại

1. **if-else**: Kiểm tra điều kiện true/false, dùng `if-else if-else` cho nhiều điều kiện
2. **switch-case**: So sánh giá trị với nhiều trường hợp, nhớ `break` để tránh fall-through  
3. **Ternary operator**: `condition ? true : false` - ngắn gọn cho điều kiện đơn giản
4. **Best practices**: Dùng `===` thay vì `==`, luôn dùng `{}` cho block statement
5. **Validation**: Kiểm tra input trước khi xử lý để tránh lỗi runtime

---

### 📚 Bài tiếp theo
👉 [**Bài 12: Vòng lặp While**](../bai-12-vong-lap-while/) - Học cách tạo vòng lặp với while và do-while!