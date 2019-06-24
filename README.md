# LẬP TRÌNH HƯỚNG ĐỐI TƯỢNG (OOP) với PHP
## ĐỐI TƯỢNG - Object?
- Đối tượng là những sự vật sự việc gắn liền với cuộc sống của chúng ta.
- Đối tượng có thể là những thứ ta có thể cảm nhận được (1 chiếc xe máy, 1 chiếc laptop, 1 cái bàn, 1 con chó, ...) hay những thứ ta không cảm nhận được(1 tài khoản, ...).
- Điển chung của đối tượng có 2 thành phần chính:
    + Đặc điểm, tính chất của đối tượng( gọi là thuộc tính - attributes)
    + Hành động, chức năng của đối tượng( gọi là phương thức - methods)
## LẬP TRÌNH HƯỚNG ĐỐI TƯỢNG - OOP?
- OOP là một ký thuật lập trình hiện đại(từ năm 2000) nhằm khác phục những điểm yếu của lập trình hướng thủ tục.
- Kĩ thuật này yêu cầu người lập trình phải quan sát các đối tượng trong tự nhiên rồi cố gắng nắm bắt những hành động cùng đặc tính của chúng, biểu diễn cúng dưới dạng 1 đối tượng ảo gồm có các thuộc tính và phương thức cần thiết để giải quyết bài toán.
- Nói một cách dễ hiểu: LTHĐT lấy đối tượng làm trung tâm, là cốt lõi để phát triển phần mềm.
## Class? Nó khác gì Object?
- Các đối tượng có các đặc tính tương tự nhau được gom lại thành 1 lớp đối tượng(Class).
- Lớp cũng có 2 thành phần chính đó là thuộc tính và phương thức.
- Lớp là một khuôn mẫu còn đối tượng là một thể hiện cụ thể dựa trên khuôn mẫu đó.
VD: - Class: Ôto, Đối tượng: (1 chiếc ôto cụ thể) chiếc Ôto này, chiếc Ôto kia, chiếc Oto của anh, chiếc Ôto của tôi,... 
## Các tính chất cơ bản của lập trình hướng đối tượng
- OOP có 4 tính chất cơ bản sau:
    + Abstraction — Trừu tượng: Tập trung vào cốt lõi của đối tượng, bỏ qua những thứ không liên quan và không quan trọng. VD: 1 đối tượng học sinh ngoài đời thực có rất nhiều thuộc tính và phương thức nhưng khi lập trình chỉ lấy những thứ cần thiết, liên quan đến bài toán.
    + Encapsulation — Đóng gói: Là không cho bên ngoài biết được bên trong đối tượng có những gì hay được cài đặt thế nào. Muốn thay đổi bên trong đối tượng thì cần được sử chấp thuận của đối tượng đó(thường thông qua các phương thức được public).
    + Inheritance — Kế thừa: Là việc kế thừa, tái sử dụng các thuộc tính và phương thức của lớp cơ sở. Lớp kế thừa được gọi là lớp con, nó sẽ thừa hưởng những gì lớp cha có và cho phép.
    + Polymorphism — Đa hình: Cùng 1 phương thức nhưng thực thi khác nhau trên các đối tượng khác nhau.

## OOP trong ngôn ngữ PHP
### Khai báo class && khởi tạo đối tượng 
```
<?php
class Human
{
    // Khai báo thuộc tính của lớp - giống khai báo biến.
    // Khai báo phương thức của lớp - giống khai báo hàm.
}

$me = new Human();
?>

- Việc khai báo thuộc tính/phương thức thường bắt đầu bằng các từ khóa biểu thị khả năng try cập:
    + private: Chỉ được sử dụng trong Class, lớp con cũng không thể sử dụng.
    + protected: giông private nhưng được kế thừa và sử dụng ở lớp con.
    + public: giống protected nhưng bên ngoài vẫ có thể sử dụng bình thường.

(còn tiếp...)
