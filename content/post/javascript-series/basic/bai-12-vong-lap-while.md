---
title: "Bài 12 - Vòng Lặp While - Lặp Khi Điều Kiện Đúng"
date: 2025-09-28T14:30:00+07:00
categories: ["JavaScript Series", "JavaScript Cơ Bản"]
tags: ["javascript-basic", "while-loop", "do-while", "loops"]
series: ["JavaScript Basic"]
series_order: 12
draft: false
image: "https://img.youtube.com/vi/E4sUJ4LvYY0/maxresdefault.jpg"
author: "Code Thu"
weight: 12
summary: "Tìm hiểu về vòng lặp while và do-while - Cách lặp code khi điều kiện còn đúng"
---

## 🎥 Video hướng dẫn chi tiết
**Nguồn:** [Khóa học JavaScript - Kteam](https://www.youtube.com/playlist?list=PL33lvabfss1ywJRoh40x9fmAfgbI1hpVX)
{{< youtube E4sUJ4LvYY0 >}}

---

## ➰ Vòng lặp while là gì?

**Vòng lặp while** thực hiện **lặp đi lặp lại** một đoạn code **khi điều kiện còn đúng**:
- 🔄 **Kiểm tra điều kiện trước** khi thực hiện
- ⏹️ **Dừng** khi điều kiện trở thành `false`
- ⚠️ **Nguy hiểm**: Có thể tạo **vòng lặp vô tận** nếu không cẩn thận
- 🎯 **Phù hợp**: Khi không biết trước số lần lặp

## 🔄 Cú pháp while loop

### Cấu trúc cơ bản:
```javascript
while (condition) {
    // Code được thực hiện khi condition = true
    // Nhớ cập nhật condition để tránh vòng lặp vô tận
}
```

### Ví dụ đơn giản:
```javascript
let count = 1;

while (count <= 5) {
    console.log("Lần thứ", count);
    count++; // Quan trọng: cập nhật count
}

console.log("Kết thúc vòng lặp, count =", count); // 6
```

### Đếm ngược:
```javascript
let countdown = 5;

while (countdown > 0) {
    console.log("Còn", countdown, "giây...");
    countdown--;
}

console.log("🚀 Khởi động!");
```

## ⚠️ Vòng lặp vô tận và cách tránh

### Ví dụ vòng lặp vô tận (NGUY HIỂM!):
```javascript
// ❌ ĐỪNG CHẠY CODE NÀY!
// let i = 1;
// while (i <= 5) {
//     console.log(i);
//     // Quên cập nhật i → i luôn = 1 → vòng lặp vô tận
// }

// ❌ Các trường hợp khác
// while (true) {
//     console.log("Vô tận!");
//     // Không có break hoặc cách thoát
// }
```

### Cách tránh vòng lặp vô tận:
```javascript
// ✅ Luôn cập nhật biến điều kiện
let i = 1;
while (i <= 5) {
    console.log(i);
    i++; // QUAN TRỌNG!
}

// ✅ Hoặc dùng safety counter
let attempts = 0;
let maxAttempts = 1000;

while (someCondition && attempts < maxAttempts) {
    // Code logic
    attempts++;
}

if (attempts >= maxAttempts) {
    console.log("Đã đạt giới hạn an toàn");
}
```

## 3. do-while loop

```javascript
// while - kiểm tra trước
let x = 10;
while (x < 5) {
    console.log("while:", x); // Không chạy vì 10 không < 5
    x++;
}

// do-while - thực hiện trước, kiểm tra sau
let y = 10;
do {
    console.log("do-while:", y); // Chạy 1 lần: "do-while: 10"
    y++;
} while (y < 5);

// Ví dụ menu chương trình
let choice;
do {
    console.log("=== MENU ===");
    console.log("1. Xem thông tin");
    console.log("2. Thoát");
    
    choice = Math.floor(Math.random() * 3) + 1; // Giả lập input
    console.log("Bạn chọn:", choice);
    
    if (choice === 1) {
        console.log("→ Hiển thị thông tin");
    } else if (choice === 2) {
        console.log("→ Thoát chương trình");
    }
    
} while (choice !== 2);
```

## 4. Ví dụ thực tế

```javascript
// Tìm kiếm trong mảng
function findInArray(array, target) {
    let index = 0;
    
    while (index < array.length) {
        if (array[index] === target) {
            return { found: true, index: index };
        }
        index++;
    }
    
    return { found: false, index: -1 };
}

// Test
let numbers = [5, 2, 8, 1, 9, 3];
let result = findInArray(numbers, 8);
console.log(result); // { found: true, index: 2 }

// Validation với while
function getValidAge() {
    let age, attempts = 0;
    
    while (attempts < 3) {
        age = Number(prompt("Nhập tuổi (0-150):"));
        
        if (!isNaN(age) && age >= 0 && age <= 150) {
            return age;
        }
        
        attempts++;
        console.log(`Tuổi không hợp lệ. Còn ${3 - attempts} lần thử`);
    }
    
    return null; // Hết lượt thử
}
```

## Chốt lại

1. **while loop**: Kiểm tra điều kiện trước khi thực hiện, lặp khi điều kiện còn `true`
2. **do-while loop**: Thực hiện ít nhất 1 lần, kiểm tra điều kiện sau
3. **Tránh vòng lặp vô tận**: Luôn cập nhật biến điều kiện, dùng safety counter
4. **Use cases**: Không biết trước số lần lặp, validation input, tìm kiếm dữ liệu
5. **Best practices**: Test kỹ logic điều kiện, luôn có cách thoát khỏi loop

---

### 📚 Bài tiếp theo
👉 [**Bài 13: Vòng lặp For**](../bai-13-vong-lap-for/) - Tìm hiểu vòng lặp for và các biến thể của nó!
