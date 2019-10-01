# Java Anotation
## Overview
```````````````````````````````````````````````````````````````````````````````
    1 - Annotation là gì và mục đích sử dụng
        1.1 - Chỉ dẫn cho trình biên dịch
        1.2 - Chỉ dẫn trong thời điểm xây dựng (Build-time)
        1.3 - Chỉ dẫn trong thời gian chạy (Runtime)
    2 - Các Annotation sẵn có của Java
        2.1 - @Deprecated
        2.2 - @Override
        2.3 - @SuppressWarnings
    3 - Viết Annotation của ban
        3.1 - Annotation đầu tiên
        3.2 - Annotation với phần tử value. (Có sự đặc biệt)
        3.3 - @Retention & @Target
        3.4 - Annotation & Reflection
    4 - Annotation Processing Tool (Kiến thức nâng cao)
```````````````````````````````````````````````````````````````````````````````

## 1. Annotation là gì và mục đích sử dụng
- __Annotation__(chú thích): cung cấp meta data cho java. __Annotation__ chỉ cung cấp metadata cho dữ liệu, do đó không làm ảnh hưởng tới việc thực thi các đoạn mã (tuy nhiên vẫn có annotation có thể ảnh hưởng trực tiếp tới code)
- Mục đích:
    - Chỉ dẫn cho trình biên dịch (Compiler)
    - Chỉ dẫn trong thời điểm xây dựng (Build-time)
    - Chỉ dẫn trong thời gian chạy (Runtime)
- 1.1: Chỉ dẫn cho trình biên dịch (Compiler): Java có sẵn 3 Annotation mà bạn có thể sử dụng để cung cấp cho các hướng dẫn để trình biên dịch Java.
    - __@Deprecated__
    - __@Override__
    - __@SuppressWarnings__
- 1.2: Chỉ dẫn trong thời điểm xây dựng (Build-time)

    Annotation có thể được được sử dụng tại thời xây dựng (Build-time), khi bạn xây dựng dự án phần mềm của bạn. Quá trình xây dựng bao gồm tạo ra các mã nguồn, biên dịch mã nguồn, tạo ra các file XML (ví dụ như mô tả triển khai), đóng gói mã biên dịch và các tập tin vào một tập tin JAR, v..v. Xây dựng phần mềm thường được thực hiện bởi một công cụ xây dựng tự động như Apache Ant hoặc Apache Maven . Xây dựng các công cụ có thể quét mã Java của bạn và dựa vào các chú thích (Annotation) của bạn để tạo ra mã nguồn hoặc các tập tin khác dựa trên những chú thích đó.

- 1.3: Chỉ dẫn trong thời gian chạy (Runtime)

    Thông thường, các Annotation không có mặt trong mã Java của bạn sau khi biên dịch. Tuy nhiên  có thể xác định các Annotation của bạn trong thời gian chạy. Các chú thích này sau đó có thể được truy cập thông qua Java Reflection, và được sử dụng để cung cấp cho các hướng dẫn chương trình của bạn, hoặc API của một số bên thứ ba (Third party API).

## 2. Các Annotation sẵn có của Java
### 2.1 @Deprecated - Chỉ dẫn cho trình biên dịch
- Đây là một Annotation dùng để chú thích một cái gì đó bị lỗi thời, tốt nhất không nên sử dụng nữa, chẳng hạn như class, hoặc method.
- Chú thích một class, method của class, attribute của class bị lỗi thời

### 2.1 @Override - Chỉ dẫn cho trình biên dịch
- Sử dụng trên các method ghi đè lại các method được sử dụng ở lớp cha. Nếu không có thì trình compiler sẽ báo lỗi là không có
- Ý nghĩa: 
    + Cho trình biên dịch + ta biết rằng method đang viết có nạp chồng từ lớp cha hay không. Nếu không có thì vẫn không báo lỗi
    + Khi mà thằng nào đó đổi tên method trong class cha => Trình biên dịch sẽ nhắc thằng đó thay tên các method khác trong lớp con

### 2.3 @SuppressWarnings - Chỉ dẫn cho trình biên dịch thôi không cảnh báo nữa, đỡ ngứa mắt