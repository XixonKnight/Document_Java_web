# 1. Kiểu dữ liệu là gì?
> Có thể hiểu kiểu dữ liệu trong ngôn ngữ lập trình là các thuộc tính ( biến ) dùng để lưu trữ thông tin, giá trị mà khi chương trình biên dịch sinh ra
## 1.1. Các kiểu dữ liệu nguyên thủy
 
| Kiểu | Mô tả | Mặc đinh | Kích thước| Ví dụ|
|:---:|:---:|:---:|:---:|:---:|
| boolean | True hoặc False| False | 1 bit | true, false |
| byte | Số nguyên từ -128 .. 127 | 0 | 8 bits | 123 |
| char | Số nguyên giá trị từ -32768 .. 32767 | 0 | 16 bits | 1000|
| int | Số nguyên -2,147,483,648 .. 2,147,483,647 | 0 | 32 bits | -2, -1, 0, 1 |
| long | Số nguyên dài | 0 | 64 bits | -2L, -1L, 0L, 1L |
| float | Số thực | 0.0 | 32 bits | 1.23e100f, -1.23e-100f, .3f, 3.14f |
| double | Số thực | 0.0 | 64 bits | 1.23456e300d, -1.23456e-300d, 1e1d |

## 1.2. Kiểu dữ liệu đối tượng
### 1.2.1. Kiểu dữ liệu đố tượng được chia làm 2 loại
* Famework định nghĩa: Kiểu dữ liệu này được tạo sẵn và công việc của chúng ta chỉ việc gọi lên và sử dụng chúng. VD: File, String, Scanner,....
* Do người dùng định nghĩa: Chính là những class được chúng ta define từ những đối tượng trong bài toán OOP. VD: Student, Teacher,...

