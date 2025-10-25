---
title: "Lập Trình Hướng Đối Tượng Trong Java"
description: "Tìm hiểu về OOP và các khái niệm cơ bản trong Java"
date: "2023-10-25"
categories: ["Java"]
tags: ["java", "oop", "lập trình"]
image: "/img/featured/featured-image.webp"
---

## Giới thiệu về OOP

Lập trình hướng đối tượng (Object-Oriented Programming - OOP) là một phương pháp lập trình dựa trên khái niệm về class và object. Java là một ngôn ngữ lập trình hướng đối tượng điển hình.

## Bốn tính chất cơ bản của OOP

### 1. Tính đóng gói (Encapsulation)

```java
public class SinhVien {
    private String maSV;
    private String hoTen;
    
    // Getter và Setter
    public String getMaSV() {
        return maSV;
    }
    
    public void setMaSV(String maSV) {
        this.maSV = maSV;
    }
}
```

### 2. Tính kế thừa (Inheritance)

```java
public class NguoiDung {
    protected String hoTen;
    protected String email;
}

public class SinhVien extends NguoiDung {
    private String maSV;
    
    public SinhVien(String hoTen, String email, String maSV) {
        this.hoTen = hoTen;
        this.email = email;
        this.maSV = maSV;
    }
}
```

### 3. Tính đa hình (Polymorphism)

```java
public interface HinhHoc {
    double tinhDienTich();
}

public class HinhVuong implements HinhHoc {
    private double canh;
    
    @Override
    public double tinhDienTich() {
        return canh * canh;
    }
}
```

### 4. Tính trừu tượng (Abstraction)

```java
public abstract class DongVat {
    public abstract void keuLenTieng();
}

public class Meo extends DongVat {
    @Override
    public void keuLenTieng() {
        System.out.println("Meo meo!");
    }
}
```

## Ví dụ thực tế

Hãy xem một ví dụ về hệ thống quản lý sinh viên đơn giản:

```java
public class QuanLySinhVien {
    private List<SinhVien> danhSachSinhVien;
    
    public void themSinhVien(SinhVien sv) {
        danhSachSinhVien.add(sv);
    }
    
    public SinhVien timKiemTheoMaSV(String maSV) {
        return danhSachSinhVien.stream()
                .filter(sv -> sv.getMaSV().equals(maSV))
                .findFirst()
                .orElse(null);
    }
}
```

## Kết luận

OOP là một phương pháp lập trình mạnh mẽ giúp code dễ bảo trì và tái sử dụng. Trong Java, việc áp dụng OOP là rất quan trọng và được sử dụng rộng rãi trong phát triển phần mềm.