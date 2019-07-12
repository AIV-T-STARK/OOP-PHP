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
```

- Việc khai báo thuộc tính/phương thức thường bắt đầu bằng các từ khóa biểu thị khả năng try cập:
    + private: Chỉ được sử dụng trong Class, lớp con cũng không thể sử dụng.
    + protected: giông private nhưng được kế thừa và sử dụng ở lớp con.
    + public: giống protected nhưng bên ngoài vẫ có thể sử dụng bình thường.

```
class Human {
    private name;
    private age;

    function Human($name, $age) {
        $this->name = $name;
        $this->age = $age;
    }
    public function Run() {
        echo $this->name . "is running....";
    }
}

$me = new Human("Gia Hao", 20);
$me->run();
```

### Kế thừa - Da Hình
```
class Human {
    protected name;
    protected age;

    function Human($name, $age) {
        $this->name = $name;
        $this->age = $age;
    }
    public function Run() {
        echo $this->name . "is running....";
    }
}

class Vietnamese extends Human {
    public funtion Run() {
        parent::Run();
        echo $this->name . "đang chạy.....";
    }
}

class Chinese extends Human {
    public funtion Run() {
        parent::Run();
        echo $this->name . "正在跑步.....";
    }
}

$Phong = new Vietnamese("Phong", 22);
$Phong->Run();
$Ztao = new Chinese("Ztao", 26);
$Ztao->Run();
```
## Overload - Override
### Overload - Nạp chồng:
- Overload đơn giản là việc tạo ra các method có cùng tên trên 1 Class, các method đó phải khác nhau về đối số đầu vào (argument) hoặc kiểu trả về. Các method này không ghi đè lên nhau mà tồn tại song song.
```
<?php 
class shape { 
      
    // __call is magic function which accepts  
    // function name and arguments 
    function __call($name_of_function, $arguments) { 
              
        // It will match the function name 
        if($name_of_function == 'area') { 
              
            switch (count($arguments)) { 
                      
                // If there is only one argument 
                // area of circle 
                case 1: 
                    return 3.14 * $arguments[0]; 
                          
                // IF two arguments then area is rectangel; 
                case 2: 
                    return $arguments[0]*$arguments[1]; 
            } 
        } 
    } 
} 
      
// Declaring a shape type object 
$s = new Shape; 
      
// Function call  
echo($s->area(2)); 
echo "\n"; 
      
// calling area method for rectangel 
echo ($s->area(4, 2)); 
?> 
```

### Override - Ghi đè:
- Override là tính năng giúp thay đổi hành vi của method, thường được sử dụng trong method ở lớp con để ghi đè lên phương thức cha có trong lớp con.
```
<?php 
  
// This is parent class 
class P { 
      
    // Function geeks of parent class 
    function geeks() { 
        echo "Parent"; 
    } 
} 
  
// This is child class 
class C extends P { 
      
    // Overriding geeks method 
    function geeks() { 
        echo "\nChild"; 
    } 
} 
  
// Reference type of parent 
$p = new P; 
  
// Reference type of child 
$c= new C; 
  
// print Parent 
$p->geeks(); 
  
// Print child 
$c->geeks(); 
?> 
```
#### Các quy tắc cho việc override:
- Các phương thức static không được override mà được mô tả lại
- Khi đối tượng lớp con gọi phương thức thì sẽ tìm phương thức trong lớp con để chạy, nếu không có thì tìm lên lớp cha
- Phương thức ghi đè không được giảm quyền truy cập so với phiên bản lớp cha. Ví dụ, không thể override 1 phương thức public bằng 1 phiên bản private.
- Phương thức private không thể bị override.

## Abstract - Interface
### Abstract
- Abstract class (Lớp trừu tượng) là 1 lớp chức các phương thức trừu tượng, các lớp khác khi kế thừa lớp trừu tượng sẽ phải định nghĩa lại các phương thức trừu tượng ấy.
- 1 lớp chỉ có thể kế thừa 1 lớp trừu tượng

```
abstract class Person
{
    protected $ten;
    protected $cmnd;
    protected $namsinh;
  
    abstract public function showInfo();
}
  
// Lớp này sai vì chưa viết lại hàm showInfo
class CongNhan extends Person
{
  
}
  
// Lớp này đúng vì ta đã khai báo, viết lại
// đầy đủ các hàm abstract
class SinhVien extends Person
{
    public function showInfo(){
  
    }
}
```
#### 1 số lưu ý khi sử dụng abstract class
- Các phương thức trừu tượng không được có code ở trong
- Không thể khởi tạo 1 đối tượng từ 1 abstract class
- Các thuộc tính không thể để ở dạng abstract

### Interface
-Interface trong hướng đối tượng là một khuôn mẫu, giúp cho chúng ta tạo ra bộ khung cho một hoặc nhiều đối tượng và nhìn vào interface thì chúng ta hoàn toàn có thể xác định được các phương thức và các thuộc tính cố định (hay còn gọi là hằng) sẽ có trong đối tượng implement nó.
```
interface DongVat
{
    //code
}
```
#### Các tính chất của Interface
- Interface không phải là 1 đối tượng, không thể được khởi tạo
- Trong interface chỉ được khai báo hằng, không được khai báo biến
- Các phương thức trong interface chỉ được khai báo chứ không được định nghĩa
- Các lớp Implement interface phải được khai báo và định nghĩa lại các phương thức trong interface đó
- 1 class có thể implement nhiều interface
- Các interface có thể kế thừa lẫn nhau
#### Các ví dụ
- Các phương thức chỉ được khai báo chứ không được định nghĩa
```
interface DongVat
{
    //đúng vì chúng ta chỉ khai báo phương thức trong interface
    public function setName();

    //Sai vì chúng ta không được định nghĩa phương thức trong interface
    public function getName()
    {
        //
    }
}
```
- Chỉ được khai báo hằng, không được khai báo biến
```
interface DongVat
{
    //đúng vì trong interface có thể khai báo hằng
    const CONNGUOI = False;

    //Sai vì trong interface không thể khai báo biến
    public $name;

}
```
- Một class có thể implement nhiều interface
```
interface DongVat
{
    public function getName();
}

interface ConTrau
{
    public function checkSung();
}

class ConNghe implements DongVat, ConTrau
{
    private $name;

    const SUNG = false;

    public function getName()
    {
        return $this->name;
    }

    public function checkSung()
    {
        return self::SUNG;
    }
}
```
- Interface có thể kế thừa lẫn nhau
```
interface DongVat
{
    public function getName();
}

interface ConTrau extends Dongvat
{
    public function checkSung();
}

class ConNghe implements ConTrau
{
    private $name;
    const SUNG = false;

    public function getName()
    {
        return $this->name;
    }

    public function checkSung()
    {
        return self::SUNG;
    }
}
```
