+++
author = "Hugo Authors"
title = "Tìm Hiểu Về Lập Trình Tổng Quát (Generics) Trong Java"
date = "2024-12-30"
description = "Hướng dẫn chi tiết về Generics trong Java và cách sử dụng để tạo mã nguồn linh hoạt và an toàn."
tags = [
"java",
"generics",
"lập trình tổng quát",
"an toàn kiểu",
]
+++

Generics là một trong những tính năng mạnh mẽ của Java, được giới thiệu từ phiên bản Java 5. Nó cho phép bạn viết mã tổng quát và linh hoạt hơn, đồng thời đảm bảo an toàn kiểu (type safety) trong thời gian biên dịch.

Generics Là Gì?
Generics cung cấp cơ chế để định nghĩa các lớp, giao diện, và phương thức có thể hoạt động với nhiều kiểu dữ liệu khác nhau mà không cần xác định kiểu cụ thể tại thời điểm viết mã.

Lợi Ích Của Generics
An Toàn Kiểu: Giảm thiểu lỗi thời gian chạy bằng cách phát hiện lỗi kiểu dữ liệu trong thời gian biên dịch.
Tái Sử Dụng Mã: Cho phép sử dụng cùng một đoạn mã cho nhiều kiểu dữ liệu khác nhau.
Đọc Dễ Hiểu Hơn: Mã nguồn rõ ràng và dễ duy trì hơn khi sử dụng Generics.
Sử Dụng Generics
1. Generics Với Lớp

```java
public class Box<T> {  
    private T item;  

    public void setItem(T item) {  
        this.item = item;  
    }  

    public T getItem() {  
        return item;  
    }  

    public static void main(String[] args) {  
        Box<String> stringBox = new Box<>();  
        stringBox.setItem("Hello Generics!");  
        System.out.println(stringBox.getItem());  

        Box<Integer> intBox = new Box<>();  
        intBox.setItem(123);  
        System.out.println(intBox.getItem());  
    }  
}  
```
2. Generics Với Phương Thức
```java
public class GenericMethodDemo {  
    public static <T> void printArray(T[] array) {  
        for (T element : array) {  
            System.out.println(element);  
        }  
    }  

    public static void main(String[] args) {  
        String[] stringArray = {"Java", "Generics", "Tutorial"};  
        Integer[] intArray = {1, 2, 3, 4, 5};  

        printArray(stringArray);  
        printArray(intArray);  
    }  
}  
```
3. Generics Với Collections
Java Collections Framework được xây dựng dựa trên Generics để đảm bảo an toàn kiểu.

```java

import java.util.ArrayList;  

public class Main {  
    public static void main(String[] args) {  
        ArrayList<String> list = new ArrayList<>();  
        list.add("Java");  
        list.add("Generics");  

        for (String item : list) {  
            System.out.println(item);  
        }  
    }  
} 
```
Giới Hạn Generics
Bạn có thể giới hạn kiểu dữ liệu sử dụng trong Generics bằng extends (cho lớp hoặc giao diện) và super (cho lớp cha).

Sử Dụng extends
```java

public class NumberBox<T extends Number> {  
    private T number;  

    public void setNumber(T number) {  
        this.number = number;  
    }  

    public T getNumber() {  
        return number;  
    }  

    public static void main(String[] args) {  
        NumberBox<Integer> intBox = new NumberBox<>();  
        intBox.setNumber(123);  
        System.out.println(intBox.getNumber());  
    }  
}  

```
Sử Dụng super Trong Wildcards
```java

import java.util.ArrayList;  

public class Main {  
    public static void printNumbers(ArrayList<? super Integer> list) {  
        for (Object obj : list) {  
            System.out.println(obj);  
        }  
    }  

    public static void main(String[] args) {  
        ArrayList<Number> numbers = new ArrayList<>();  
        numbers.add(1);  
        numbers.add(2.5);  

        printNumbers(numbers);  
    }  
}  
```
Kết Luận
Generics giúp Java trở thành một ngôn ngữ an toàn kiểu và linh hoạt hơn. Bằng cách tận dụng Generics, bạn có thể viết mã nguồn tối ưu, tái sử dụng cao, và giảm thiểu lỗi trong thời gian chạy. Hãy thực hành nhiều để làm quen với các tình huống sử dụng khác nhau của Generics trong Java!













