+++
author = "Hugo Authors"
title = "Các Kiểu Dữ Liệu trong Java"
date = "2024-12-30"
description = "Tìm hiểu về các kiểu dữ liệu cơ bản và nâng cao trong Java"
tags = [
"java",
"kiểu dữ liệu",
"lập trình",
]
+++

Kiểu dữ liệu là một phần quan trọng trong bất kỳ ngôn ngữ lập trình nào. Trong Java, kiểu dữ liệu được chia thành hai loại chính: kiểu dữ liệu nguyên thủy (primitive) và kiểu dữ liệu tham chiếu (reference).

Kiểu Dữ Liệu Nguyên Thủy

Java cung cấp 8 kiểu dữ liệu nguyên thủy, được sử dụng để lưu trữ giá trị đơn giản:

byte:

Kích thước: 1 byte

Phạm vi: -128 đến 127

byte num = 100; 

short:

Kích thước: 2 byte

Phạm vi: -32,768 đến 32,767

short num = 1000; 

int:

Kích thước: 4 byte

Phạm vi: -2^31 đến 2^31-1

int num = 100000; 

long:

Kích thước: 8 byte

Phạm vi: -2^63 đến 2^63-1

long num = 100000L; 

float:

Kích thước: 4 byte

Phạm vi: ~3.4e-038 đến 3.4e+038

float num = 5.75f; 

double:

Kích thước: 8 byte

Phạm vi: ~1.7e-308 đến 1.7e+308

double num = 19.99; 

char:

Kích thước: 2 byte

Lưu trữ một ký tự Unicode

char letter = 'A'; 

boolean:

Giá trị: true hoặc false

boolean isJavaFun = true; 

Kiểu Dữ Liệu Tham Chiếu

Kiểu dữ liệu tham chiếu được sử dụng để lưu trữ địa chỉ của các đối tượng. Các kiểu phổ biến bao gồm:

String: Đại diện cho một chuỗi ký tự.

String message = "Hello, Java!"; 

Array: Lưu trữ một tập hợp các phần tử có cùng kiểu.

int[] numbers = {1, 2, 3, 4, 5}; 

Class: Lưu trữ đối tượng của một lớp.
```java

class Person { 
    String name; 
    int age; 
} 
Person person = new Person(); 
```
Interface: Thể hiện hành vi của lớp.

Ép Kiểu Dữ Liệu

Java hỗ trợ hai loại ép kiểu:

Ép kiểu ngầm định: Tự động chuyển đổi kiểu nhỏ hơn sang kiểu lớn hơn.

int myInt = 9; 
double myDouble = myInt; // Ép kiểu ngầm định 

Ép kiểu tường minh: Chuyển đổi kiểu lớn hơn sang kiểu nhỏ hơn.

double myDouble = 9.78; 
int myInt = (int) myDouble; // Ép kiểu tường minh 

Tính Năng của Kiểu Dữ Liệu Java

Kiểu tĩnh (Static Typing): Kiểu dữ liệu được xác định tại thời điểm biên dịch, giúp phát hiện lỗi sớm.

Không có con trỏ trực tiếp: Đảm bảo an toàn bộ nhớ.

Hỗ trợ kiểu dữ liệu không thay đổi (Immutable): Ví dụ, chuỗi trong Java là không thay đổi.

Kết Luận

Hiểu rõ về các kiểu dữ liệu trong Java là nền tảng quan trọng để xây dựng các chương trình mạnh mẽ và hiệu quả. Hãy thực hành và áp dụng chúng vào các dự án thực tế để nắm vững hơn.

