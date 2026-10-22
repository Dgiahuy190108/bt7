## Phần 1: Phân tích lỗi

### 1. Cơ chế quét và lỗi định dạng thủ công

-   **Cơ chế hoạt động của Auto TOC:** Tính năng Mục lục tự động (Table of Contents) của Microsoft Word không quét văn bản dựa trên **hình thức trực quan** (như chữ to, in đậm, tô màu hay tô vàng), mà quét dựa trên **mã định dạng kiểu đoạn văn (Paragraph Style)** được gán ngầm bên trong cấu trúc file, cụ thể là các style chuẩn:  `Heading 1`,  `Heading 2`, và `Heading 3`.
    
-   **Nguyên nhân gây lỗi:** Các tiêu đề trong file hiện tại đang được định dạng thủ công trực tiếp trên font chữ (Normal + in đậm, đổi cỡ chữ, tô vàng). Đối với phần mềm Word, các dòng này vẫn chỉ được tính là văn bản thường (`Normal`). Khi chạy lệnh chèn TOC, Word quét không thấy bất kỳ đoạn nào mang nhãn Heading nên kết quả trả về là một dòng trống.
    

### 2. Tác hại của việc nhầm cấp Heading (Ví dụ: `2.1.1. Tiểu ban Kỹ thuật`)

-   **Ảnh hưởng đến cấu trúc:** Mục lục tự động dựa vào cấp độ Heading để phân cấp hình ảnh trực quan và độ thụt lề (indentation):
    
    -   `Heading 1`: Sát lề trái (Cấp chương).
        
    -   `Heading 2`: Thụt vào 1 nấc (Cấp phần mục con).
        
    -   `Heading 3`: Thụt sâu hơn nữa (Cấp chi tiết nhỏ).
        
-   **Hậu quả:** Nếu gán nhầm dòng `2.1.1. Tiểu ban Kỹ thuật` thành `Heading 2` thay vì `Heading 3`, mục này sẽ hiển thị ngang hàng với các mục `1.1`,  `1.2` và `2.1` trong bảng mục lục thay vì nằm thụt lề con bên trong mục `2.1`. Điều này làm sai lệch hoàn toàn cấu trúc tài liệu SRS (Software Requirements Specification) và gây rối mắt cho ban giám khảo khi tra cứu.
    

## Phần 2: Sửa lỗi & Nghiệm thu

### 3. Hướng dẫn sửa cấu trúc Heading cho 7 dòng tiêu đề

Sử dụng các phím tắt nhanh đã được Word hỗ trợ sẵn để gán đúng cấp độ cho từng dòng tiêu đề:

-   `Ctrl + Alt + 1`: Gán Heading 1
    
-   `Ctrl + Alt + 2`: Gán Heading 2
    
-   `Ctrl + Alt + 3`: Gán Heading 3
    

Dòng tiêu đề

Thao tác thực hiện

Định dạng đích

**1. Thông tin chung hội nghị**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 1`**

Heading 1

**1.1. Tên hội nghị**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 2`**

Heading 2

**1.2. Thời gian & địa điểm**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 2`**

Heading 2

**2. Cơ cấu ban tổ chức**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 1`**

Heading 1

**2.1. Ban Nội dung**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 2`**

Heading 2

**2.1.1. Tiểu ban Kỹ thuật**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 3`**

Heading 3

**3. Lịch trình sự kiện**

Đặt con trỏ chuột vào dòng này, nhấn **`Ctrl + Alt + 1`**

Heading 1

**Cách nghiệm thu:** Sau khi hoàn tất gán cho cả 7 dòng, vào thẻ **References** → chọn **Table of Contents** → chọn mẫu mục lục tự động (hoặc nhấn nút **Update Table** nếu đã chèn sẵn). Mục lục sẽ hiển thị đầy đủ cấu trúc 3 cấp Chương → Mục → Chi tiết với đúng độ thụt lề.

### 4. Xử lý bẫy thay đổi số trang (`3. Lịch trình sự kiện` dịch từ trang 2 sang trang 4)

-   **Vấn đề:** Khi nội dung phình ra làm thay đổi số trang, mục lục cũ **không tự động cập nhật** số trang mới ngay lập tức (vẫn giữ số trang cũ ở trang 2).
    
-   **Thao tác cần làm:**
    
    1.  Click chọn toàn bộ vùng bảng Mục lục.
        
    2.  Bấm nút **Update Table** xuất hiện ở góc trên bên trái bảng mục lục (hoặc nhấn chuột phải vào mục lục và chọn **Update Field**).
        
    3.  Chọn ô **Update entire table** (Cập nhật toàn bộ bảng) để Word quét lại toàn bộ tài liệu và cập nhật chính xác số trang mới (sang trang 4) cho mục "3. Lịch trình sự kiện".
        
-   **Phím tắt nhanh:** Nhấp chuột vào bảng mục lục và nhấn phím **`F9`**, sau đó chọn **Update entire table** và nhấn **OK**.
