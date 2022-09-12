## Kiểm tra JPA
## Thời gian: 90 phút
## Cách nộp bài: Mọi người trả lời câu hỏi ngay dưới câu trả lời, sau đó tạo project trong github (public) rồi update file Kiem Tra JPA.md này và source code lên, sau đó gửi link github cho giáo viên
## Project github có tên: KiemTraJPA_HoTen (Ví dụ: KiemTraJPA_NguyenVanNam)

### Câu 1
Annotation @Entity để làm gì?
A. Khai báo map với tên bảng trong DB
B. Khai báo class là 1 entity để làm việc với DB
C. Khai báo tên cột trong 1 bảng của DB

### Câu 2
Annotation @Table để làm gì?
A. Khai báo map với tên bảng trong DB
B. Khai báo class là 1 entity để làm việc với DB
C. Khai báo tên cột trong 1 bảng của DB

### Câu 3
Annotation @Repository để làm gì?
A. Khai báo class hiện tại là 1 repository để làm việc với DB
B. Khai báo class là 1 entity để làm việc với DB
C. Khai báo tên cột trong 1 bảng của DB

### Câu 4
Thuộc tính nào trong @Column để khai báo cột đó không được nhận giá trị null?
A. nullable = false
B. nullable = true
C. name = "name"
D. unique = true

### Câu 5
Thuộc tính nào trong @Column để khai báo giá trị cột đó là duy nhất?
A. nullable = false
B. nullable = true
C. name = "name"
D. unique = true

### Câu 6
Câu nào đúng về annotation @Id?
A. Khi dùng @Id để tạo key cho table, bắt buộc phải dùng kèm @GeneratedValue
B. Khi dùng @Id để tạo key cho table, chỉ có thể tạo property id là kiểu số
C. Khi tạo id cho entity, kiểu @GeneratedValue(strategy = GenerationType.AUTO) là kiểu tạo ra dữ liệu kiểu string do chúng ta tự custom
D. Khi dùng @GeneratedValue loại sequence, có thể set giá trị id đầu tiên theo ý mình

### Câu 7
Giả sử có 1 class Employee với các fields sau {id, emailAddress, firstName, lastName}. Hãy viết các method trong interface EmployeeRespository để :
#### Tìm tất cả các Employee theo emailAddress
#### Tìm tất cả các Employee khác nhau th eo firstName hoặc lastName

### Câu 8
Trong những method sau, phương thức nào là sử dụng NamedQuery?
A.
@Query("FROM Product WHERE productName = 'Ô tô'")
List<Product> findDataFromDb();
B.
List<Product> findByProductName();
C.
@Query("SELECT * FROM product WHERE product_name = 'Ô tô'", nativeQuery = true)
List<Product> findDataToShow();

### Câu 9
public class Category {
	...
	@OneToMany(mapBy="category")
	private List<Product> products;
}

public class Product {
	...
	@ManyToOne
	@JoinColumn(name = "category_id")
	private Category category;
}
Chọn mô tả đúng?

A. Đoạn code trên sẽ tạo ra 1 cột category_id trong bảng category
B. Đoạn code trên sẽ tạo ra 1 cột category_id trong bảng product
C. Đoạn code trên thiếu @JoinColumn ở class Category

### Câu 10
@Transaction dùng để làm gì?
A. Dùng để tạo transaction, có transaction mới có thể tương tác với DB
B. Để tạo ra câu truy vấn để tương tác với DB
C. Để toàn vẹn dữ liệu khi cập nhật dữ liệu (thêm, sửa xoá) vào Db

### Câu 11
Câu nào đúng về quan hệ nhiều nhiều?
A. Quan hệ nhiều nhiều giữa 2 entity Category và Product phải cần 1 entity category_product nữa mới có thể thao tác được.
B. Quan hệ nhiều nhiều chỉ có thể dùng 2 annotation @ManyToMany ở 2 entity Category và Product.
C. Quan hệ nhiều nhiều giữa 2 entity Category và Product có thể dùng 2 annotation @OneToMany và @ManyToOne.

### Câu 12
Câu nào đúng về phân trang?
#### A. Phân trang trong Spring Data Jpa bắt buộc phải gửi 3 tham số page, size, sort
#### B. Khi dùng phân trang thì trang đầu tiên mặc định trong Spring Data Jpa là trang 1
#### C. Phân trang trong Spring Data Jpa không bắt buộc phải gửi 3 tham số page, size, sort

### Bài Tập Code
![Alt](https://raw.githubusercontent.com/nguyenvantuyen6789/kiem-tra-jpa/main/OneToMany.png)
#### Tạo 2 Entity Product(id, productName, quantity(số lượng)), Category (id, categoryName)
#### Hãy bổ sung quan hệ One to Many giữa bảng Category, Product (1 category có nhiều product)
#### Viết Api CRUD category, CRUD product
