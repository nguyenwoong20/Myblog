---
title: "Bài 8 - Abstract Class Trong Java - Quá Chi Là TRỪU TƯỢNG"
date: 2025-09-22T17:00:00+07:00
categories: ["Java Series", "Java Nâng Cao"]
tags: ["java-advanced", "oop"]
series: ["Java Advanced"]
series_order: 8
draft: false
image: "https://img.youtube.com/vi/Hbp2zLIqmak/maxresdefault.jpg"
---

## 🎥 Video minh họa nguồn: YTB Code Thu
{{< youtube Hbp2zLIqmak >}}

---

## 1) Abstract Class là gì?
- Là class được khai báo với từ khóa `abstract`
- Không thể tạo instance trực tiếp từ abstract class
- Có thể chứa cả abstract method và method thường
- Được dùng làm base class cho các class khác

## 2) Abstract Method
- Method được khai báo nhưng không có implementation
- Các class con phải override tất cả abstract methods

```java
public abstract class Animal {
    // Abstract method - không có implementation
    public abstract void makeSound();
    
    // Method thường - có implementation
    public void eat() {
        System.out.println("Eating...");
    }
}

class Dog extends Animal {
    @Override
    public void makeSound() {
        System.out.println("Woof!");
    }
}
```

## 3) Đặc điểm của Abstract Class

### 3.1. Không thể tạo instance
```java
// Sai - không thể tạo instance
Animal animal = new Animal();

// Đúng - tạo instance từ class con
Animal animal = new Dog();
```

### 3.2. Có thể có constructor
```java
public abstract class Shape {
    private String color;
    
    // Constructor trong abstract class
    public Shape(String color) {
        this.color = color;
    }
    
    public abstract double calculateArea();
}

class Circle extends Shape {
    private double radius;
    
    public Circle(String color, double radius) {
        super(color); // Gọi constructor của abstract class
        this.radius = radius;
    }
    
    @Override
    public double calculateArea() {
        return Math.PI * radius * radius;
    }
}
```

### 3.3. Có thể có fields và methods thường
```java
public abstract class Database {
    protected String connectionString;
    
    // Method thường
    public void connect() {
        System.out.println("Connecting to " + connectionString);
    }
    
    // Abstract method
    public abstract void query();
}
```

## 4) Khi nào dùng Abstract Class?

### 4.1. Template Method Pattern
```java
public abstract class Game {
    // Template method
    public final void play() {
        initialize();
        startPlay();
        endPlay();
    }
    
    // Hooks
    abstract void initialize();
    abstract void startPlay();
    abstract void endPlay();
}
```

### 4.2. Common Base Functionality
```java
public abstract class Vehicle {
    protected String brand;
    protected String model;
    
    public String getInfo() {
        return brand + " " + model;
    }
    
    abstract void start();
}
```

## 5) Abstract Class vs Interface

### Abstract Class
- Có thể có fields không static và non-final
- Có thể có method implementation
- Một class chỉ extend được một abstract class
- Có thể có constructor
- Access modifiers đa dạng

### Interface
- Fields luôn là static và final
- Methods mặc định là abstract (Java 8+ có default methods)
- Một class có thể implement nhiều interface
- Không có constructor
- Methods luôn là public

## 6) Best Practices

### 6.1. Sử dụng Template Method Pattern
```java
public abstract class DataMiner {
    public final void mine() {
        openFile();
        extractData();
        parseData();
        closeFile();
    }
    
    abstract void extractData();
    abstract void parseData();
}
```

### 6.2. Cung cấp implementation mặc định
```java
public abstract class Logger {
    // Default implementation
    public void log(String message) {
        System.out.println("Default: " + message);
    }
    
    // Must be implemented
    abstract void logError(String error);
}
```

## 7) Kết luận & cảm nhận
- Abstract class là công cụ mạnh mẽ cho code tái sử dụng
- Kết hợp tốt với Template Method Pattern
- Cần cân nhắc giữa abstract class và interface

## Tiếp theo: [Interface trong Java](/p/java_interface/)
