---
title: "Bài 6 - Java OOP: Lớp, Đối tượng, Kế thừa, Đa hình"
date: 2025-09-22T10:10:00+07:00
categories: ["Java", "Java Nâng Cao"]
slug: "java_bai6"
series: ["Java cơ bản"]
draft: false
---

Bài này giúp bạn nắm 4 trụ cột OOP trong Java: đóng gói, kế thừa, đa hình, trừu tượng.

## 1) Lớp và Đối tượng
```java
public class Student {
    private String name;   // đóng gói qua private + getter/setter
    private int age;

    public Student(String name, int age) {
        this.name = name;
        this.age = age;
    }

    public String getName() { return name; }
    public void setName(String name) { this.name = name; }

    public int getAge() { return age; }
    public void setAge(int age) { this.age = age; }

    public String info() {
        return name + " - " + age;
    }
}
```

## 2) Kế thừa (Inheritance)
```java
class Person {
    public String name;
    public String hello() { return "Hello, I'm " + name; }
}

class Employee extends Person {
    public String role;
}

// Employee có thuộc tính/method của Person
```

## 3) Đa hình (Polymorphism)
```java
class Animal { public String sound() { return "..."; } }
class Dog extends Animal { @Override public String sound() { return "Gâu"; } }
class Cat extends Animal { @Override public String sound() { return "Meo"; } }

public class Zoo {
    public static void main(String[] args) {
        Animal a1 = new Dog();
        Animal a2 = new Cat();
        // Gọi sound() sẽ phụ thuộc kiểu thực sự tại runtime
        System.out.println(a1.sound());
        System.out.println(a2.sound());
    }
}
```

## 4) Trừu tượng (Abstraction)
```java
abstract class Shape {
    abstract double area();
}

class Circle extends Shape {
    private double r;
    Circle(double r) { this.r = r; }
    @Override double area() { return Math.PI * r * r; }
}
```

## 5) Interface vs Abstract class
- Interface: xác định hợp đồng hành vi; lớp triển khai phải override toàn bộ method mặc định.
- Abstract class: cho phép chứa state, method có sẵn và method trừu tượng.

```java
interface Flyable { void fly(); }

class Bird implements Flyable {
    public void fly() { System.out.println("Flap"); }
}
```

## 6) Gợi ý thiết kế
- Ưu tiên composition hơn inheritance nếu quan hệ không phải "là một" (is-a).
- Field nên là `private`, expose qua getter/setter hoặc constructor.
- Dùng `@Override` để tránh lỗi ghi đè sai chữ ký method.

---

Trước đó: [Bài 5 – Hàm & phương thức](/Myblog/p/java_bai5/)

Tiếp theo: [Bài 7 – Exception](/Myblog/p/java_bai7/)

