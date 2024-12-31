+++
author = "Hugo Authors"
title = "Khám Phá Stream API Trong Java 8"
date = "2024-12-30"
description = "Hướng dẫn toàn diện về Stream API và cách sử dụng để xử lý dữ liệu hiệu quả trong Java."
tags = [
"java",
"stream api",
"java 8",
"lập trình hàm",
"xử lý dữ liệu",
]
+++

Stream API là một trong những tính năng đáng chú ý được giới thiệu trong Java 8. Nó cung cấp cách tiếp cận lập trình hàm để xử lý dữ liệu, giúp mã nguồn ngắn gọn, dễ đọc và hiệu quả hơn.

Stream API Là Gì?
Stream API là một công cụ mạnh mẽ để xử lý tập hợp dữ liệu (Collections) và mảng (Arrays) trong Java. Nó hoạt động dựa trên mô hình dòng dữ liệu (streams), cho phép thực hiện các thao tác như lọc, ánh xạ, sắp xếp, và thu gọn dữ liệu một cách dễ dàng.

Đặc Điểm Của Stream
Không Thay Đổi Dữ Liệu Gốc: Stream không làm thay đổi nguồn dữ liệu ban đầu mà tạo ra một dòng dữ liệu mới.
Thực Thi Lười (Lazy Evaluation): Các thao tác trên Stream chỉ được thực thi khi có một thao tác đầu ra (terminal operation).
Hỗ Trợ Xử Lý Song Song: Stream có thể được xử lý đồng thời bằng cách sử dụng parallelStream().
Tạo Stream
1. Từ Collection
```java

import java.util.Arrays;  
import java.util.List;  

public class Main {  
    public static void main(String[] args) {  
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie");  
        names.stream().forEach(System.out::println);  
    }  
}  
```
2. Từ Array
```java

import java.util.stream.Stream;  

public class Main {  
    public static void main(String[] args) {  
        String[] array = {"Java", "Stream", "API"};  
        Stream.of(array).forEach(System.out::println);  
    }  
} 
``` 
3. Từ Giá Trị (Values)
```java

import java.util.stream.Stream;  

public class Main {  
    public static void main(String[] args) {  
        Stream.of("Hello", "World").forEach(System.out::println);  
    }  
}  
```
Các Hoạt Động Trên Stream
1. Hoạt Động Trung Gian (Intermediate)
Lọc Dữ Liệu (filter)
```java

import java.util.Arrays;  
import java.util.List;  

public class Main {  
    public static void main(String[] args) {  
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);  
        numbers.stream()  
               .filter(n -> n % 2 == 0)  
               .forEach(System.out::println);  
    }  
}  
```
Ánh Xạ (map)
```java

import java.util.Arrays;  
import java.util.List;  

public class Main {  
    public static void main(String[] args) {  
        List<String> names = Arrays.asList("alice", "bob", "charlie");  
        names.stream()  
             .map(String::toUpperCase)  
             .forEach(System.out::println);  
    }  
} 
``` 
Sắp Xếp (sorted)
```java

import java.util.Arrays;  
import java.util.List;  

public class Main {  
    public static void main(String[] args) {  
        List<Integer> numbers = Arrays.asList(5, 1, 3, 2, 4);  
        numbers.stream()  
               .sorted()  
               .forEach(System.out::println);  
    }  
}  
```
2. Hoạt Động Kết Thúc (Terminal)
Thu Gọn (reduce)
```java

import java.util.Arrays;  
import java.util.List;  

public class Main {  
    public static void main(String[] args) {  
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);  
        int sum = numbers.stream().reduce(0, Integer::sum);  
        System.out.println("Tổng: " + sum);  
    }  
}  

```
Thu Gom (collect)
```java

import java.util.Arrays;  
import java.util.List;  
import java.util.stream.Collectors;  

public class Main {  
    public static void main(String[] args) {  
        List<String> names = Arrays.asList("Alice", "Bob", "Charlie");  
        List<String> filteredNames = names.stream()  
                                          .filter(name -> name.startsWith("A"))  
                                          .collect(Collectors.toList());  
        System.out.println(filteredNames);  
    }  
}  
```
Xử Lý Song Song Với parallelStream()
```java

import java.util.Arrays;  
import java.util.List;  

public class Main {  
    public static void main(String[] args) {  
        List<Integer> numbers = Arrays.asList(1, 2, 3, 4, 5);  
        numbers.parallelStream()  
               .map(n -> n * n)  
               .forEach(System.out::println);  
    }  
}  
```
Kết Luận
Stream API là công cụ mạnh mẽ để xử lý dữ liệu trong Java, giúp viết mã nguồn ngắn gọn, hiệu quả, và dễ duy trì hơn. Bằng cách sử dụng Stream API, bạn có thể thực hiện các thao tác phức tạp trên dữ liệu một cách đơn giản và dễ hiểu.