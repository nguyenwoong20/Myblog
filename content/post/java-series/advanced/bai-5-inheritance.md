---
title: "Bài 5 - Thống Trị Tính Kế Thừa (Inheritance) Trong Java"
date: 2025-09-22T15:30:00+07:00
categories: ["Java Series", "Java Nâng Cao"]
tags: ["java-advanced", "oop"]
series: ["Java Advanced"]
series_order: 5
draft: false
image: "https://img.youtube.com/vi/8h42m579ez4/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube 8h42m579ez4 >}}

---

## 1) Kế thừa là gì?
Kế thừa là cơ chế cho phép một class (subclass) kế thừa các thuộc tính và phương thức từ một class khác (superclass).

## 2) Cú pháp kế thừa
```java
class Animal {
    protected String name;
    
    public void eat() {
        System.out.println(name + " is eating");
    }
}

class Dog extends Animal {
    public void bark() {
        System.out.println(name + " says: Woof!");
    }
}
```

## 3) Các loại kế thừa

### 3.1. Single Inheritance
Một class kế thừa từ một class duy nhất.
```java
class A {}
class B extends A {}
```

### 3.2. Multilevel Inheritance
Kế thừa nhiều cấp.
```java
class Animal {}
class Mammal extends Animal {}
class Dog extends Mammal {}
```

### 3.3. Hierarchical Inheritance
Nhiều class cùng kế thừa từ một class.
```java
class Animal {}
class Dog extends Animal {}
class Cat extends Animal {}
```

## 4) Method Overriding
Con có thể ghi đè phương thức của cha.

```java
class Animal {
    public void makeSound() {
        System.out.println("Some sound");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof!");
    }
}
```

## 5) Từ khóa final
- Ngăn kế thừa: `final class`
- Ngăn override: `final method`

```java
final class Constants {
    // Không thể kế thừa từ class này
}

class Animal {
    final void breathe() {
        // Không thể override phương thức này
    }
}
```

## 6) Best Practices

### 6.1. Composition over Inheritance
Ưu tiên dùng composition khi có thể.

```java
// Inheritance
class ElectricCar extends Car {}

// Composition (better)
class Car {
    private Engine engine;
}
```

### 6.2. Programming to Interface
```java
// Instead of
Dog dog = new Dog();

// Better
Animal dog = new Dog();
```

### 6.3. Liskov Substitution Principle
Class con phải có thể thay thế class cha mà không gây lỗi.

## 7) Những điều cần tránh
1. Kế thừa quá nhiều tầng
2. Override method mà không giữ đúng tính chất của lớp cha
3. Lạm dụng kế thừa khi không cần thiết

## 8) Kết luận & cảm nhận
- Kế thừa là công cụ mạnh mẽ nhưng cần dùng đúng chỗ
- Ưu tiên composition trong nhiều trường hợp
- Tuân thủ SOLID principles khi thiết kế kế thừa

## Tiếp theo: [Tính Đóng Gói trong Java](/Myblog/p/java_encapsulation/)