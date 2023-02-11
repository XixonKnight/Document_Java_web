# 1. Lập trình hướng đối tượng (Oriented Object Programming - OOP) là gì?

* Lập trình hướng đối tượng là một mô hình lập trình máy tính dựa trên khai niệm lớp và đối tượng
* Lấy đối tượng làm nền tảng để xây dựng giải thuật, xây dựng chương trình và thực hiện xử lý dữ liệu với đối tượng đã định nghĩa đó
* Nhằm tối ưu việc sử dụng mã nguồn(source code), tái sử dụng mã nguồn, tóm gọn các thủ tục đã biết trước tính chất thông qua việc sử dụng đối tượng

# 2. Các thành phần của OOP
* Class: Là sự trừu tượng hóa. Là khuôn mẫu của tập hợp các đối tượng có cùng thuộc tính(attibutes) và hành vi(method). Cấu trúc của một lớp bao gồm:
  * Phạm vi truy cập(access modfier): Phạm vi truy cập của lớp, thuộc tính và phương thức
  * Tên lớp(class name): Mỗi class để có một tên riêng để phân biệt với các class cùng phạm vi
  ```java
  <access modifier> class <ClassName>{}
  ```
  * Các thuộc tính(attibutes): Mô tả các trường dữ liệu cho mỗi đối tượng mà class đang định nghĩa hay lưu các tham chiếu đến đối tượng của class khác
  ```c
  public class A{
    // Các trường lưu dữ liệu cho mỗi đối tượng:
    private int y, z;
    
    // Tham chiếu đến đối tượng x từ lớp B
    private B x;
    }
  ```
  * Các phương thức(method): Mỗi method của class thực chất là một hàm được viết riêng cho các đối tượng của class và được gọi lên để tác động lên đối tượng của class đó
  ```java
  // Lớp Err
    public class Err{
        // Các thuộc tính
        private String title;
        private String mess;
        
        // Phương thức
        public void inputData(String tt, String m){
            title = tt;
            mess = m;
        }
        
        public void output(){
            System.out.println("Err " + title + ": " + mess);
        }
    }

    // Hàm main
    public static void main(String args[]){
        // Khai báo, khởi tạo đối tượng
        Err x = new Err();
        
        // Tác động vào đối tượng
        x.input("Error 2001", "- Lỗi này tạm thời chưa có nội dung");
        x.output();
    }
  ```
  * Đối tượng(Object): trong lập trình hướng đối tượng, một thực thể được coi là đối tượng khi nó có các thuộc tính và các hành vi.
  ```java
  // Định nghĩa lớp đối tượng Person
    public class Person{
        // khai báo một vài thuộc tính (attributes)
        private String name;
        protected String age;
        double height;

        // Khai báo các hành vi (methods)
        public void moving(){
            // di chuyển
        }

        public void eating(){
            //ăn
        }

        public void drinking(){
            // uống
        }

        public void sleeping(){
            //ngủ
        }
        //...
    }

    // Hàm main
    public static void main(String args[]){
        // Khởi tạo một đối tượng thuộc lớp Person
        Person x = new Person();
        // ở đây x chính là 1 đối tượng, có đầy đủ các thuộc tính và hành vi trong lớp Person.
    }
  ```
# 3. Access Modifier
* OOP Java gồm 4 phạm vi truy cập cho class:
  * private: Chỉ cho phép truy cập nội bộ trong class.
  * protected: cho phép truy cập được từ trong hay cả ngoài package, nếu ngoài package thì phải thông qua tính kế thừa. private và protected đều chỉ áp dụng bên trong class như thuộc tính và phương thức... Không thể áp dụng cho phạm vi truy cấp của class hoặc interface
  ```java
    // Định nghĩa lớp X trong gói a
    package a;
    public class X{
        protected int x1, x2;

        protected int plus(){
            return x1 + x2;
        }
    }

    // Định nghĩa lớp Y trong gói a
    package a;
    public class Y{
        public static main(String args[]){
        X c = new X();
        c.x1 = 1;
        c.x2 = 2;
        System.out.print(c.plus());
        // Ta có thể thấy rằng chúng ta hoàn toàn truy xuất được đến các thuộc tính hay phương thức có trong X
        }
    }

    // Định nghĩa lớp Z trong gói b
    package b;
    public class Z extends a.X {
        public static main(String args[]){
        Z c = new X();
        c.x1 = 1;
        c.x2 = 2;
        System.out.print(c.plus());
        // Khi này để truy xuất được đến các thuộc tính, phương thức trong X ta cần để Z kế thừa X.
        }
    }

  ``` 
  * default: Là phạm vi khi khai báo không cần ghi gì cả. Chỉ cho phép truy cập trong cùng package
  * public: Bất cứ chỗ nào trong project đều có thể truy cập đến được