# Đỗ Ngọc Hải k235480106019
## YÊU CẦU CHUNG CỦA BÀI TẬP 02

1. **Nội dung:**

  - Sinh viên thực hiện các yêu cầu dưới đây trên hệ quản trị SQL Server. Mỗi bước thực hiện cần chụp ảnh màn hình (screenshot) minh họa
  - Ảnh chụp phải bao gồm cả mã SQL và kết quả thực thi.
  - Mỗi ảnh phải có chú thích rõ ràng: Ảnh này làm gì? Lệnh SQL đó giải quyết vấn đề gì? Kết quả nói lên điều gì?

2. **Sản phẩm nộp:**
  - Đẩy lên repository GitHub cá nhân (để chế độ Public). Repository gồm 2 file:
  - README.md: Chứa nội dung bài làm, các đoạn code và các ảnh chụp minh họa (dùng cú pháp Markdown để chèn ảnh).
  - baikiemtra2.sql: File script chứa toàn bộ mã nguồn SQL đã viết.

3. **Hình thức chấm:**
  - Giảng viên sẽ kiểm tra tính đúng đắn của logic, cách đặt tên theo quy chuẩn và đối soát thời gian lưu vết trên GitHub (Commit history).

4. **Deadline:** 23:59:59 ngày 03 tháng 5 năm 2026. (hạn rất dài, muộn là quá lười)

## NỘI DUNG YÊU CẦU (GỒM 5 PHẦN):

### Phần 1: Thiết kế và Khởi tạo Cấu trúc Dữ liệu (Kiến thức 6, 7) 

  + Sinh viên tự chọn một chủ đề quản lý (Ví dụ: Quản lý thư viện, Quản lý khách sạn, hoặc Quản lý dự án, HOẶC BẤT KỲ BÀI TOÁN QUẢN LÝ NÀO KHÁC).

  + Tạo một Database mới với tên [Tên dự án]_[MaSV].  //LƯU Ý PHẢI CÓ MÃ SV CÁ NHÂN Ở TÊN CỦA DB ĐÚNG NHƯ YÊU CẦU, vd: QuanLyKhachSan_K123456789

  + Tạo ít nhất 3 bảng có quan hệ với nhau. Yêu cầu:

  + Sử dụng đa dạng các kiểu dữ liệu (Số nguyên, số thực, chuỗi ký tự Unicode, ngày tháng, tiền tệ, ...).

  + Áp dụng đúng quy tắc đặt tên (BướuLạcĐà).

  + Sử dụng cặp ngoặc [ ] để bọc tên bảng và tên trường trong script khởi tạo.

  + Có giải thích chỗ nào là PK, chỗ nào là FK, trường nào có ràng buộc cứng CK (ví dụ điểm từ 0..10),...

### Phần 2: Xây dựng Function (Kiến thức 8, 9) 

  + Hãy cho biết trong SQL Server có những loại function build_in (hàm có sẵn) nào, nêu 1 vài system function build_in mà em tìm hiểu được (ko cần nhiều, cần đặc sắc theo góc nhìn của em), cho SQL khai thác các hàm đó.

  + Hàm do người dùng tự viết trong SQL thường mang mục đích gì? Nó có những loại nào? Mỗi loại thường được dùng khi nào? Tại sao có nhiều system function rồi mà vẫn cần tự viết fn riêng?

  + Viết 01 Scalar Function (Hàm trả về một giá trị): Đưa ra 1 logic cho cơ sở dữ liệu của em, mà cần dùng đến function này. (SV TỰ NGHĨ RA YÊU CẦU CỦA HÀM VÀ VIẾT HÀM GIẢI QUYẾT NÓ)

    Sau khi đã có hàm, viết câu lệnh sql khai thác hàm đó.

  + Viết 01 Inline Table-Valued Function: Trả về danh sách các bản ghi theo một điều kiện lọc cụ thể (SV TỰ NGHĨ RA YÊU CẦU CỦA HÀM VÀ VIẾT HÀM GIẢI QUYẾT NÓ)

    Sau khi đã có hàm, viết câu lệnh sql khai thác hàm đó.

  + Viết 01 Multi-statement Table-Valued Function: Thực hiện xử lý logic phức tạp bên trong (có sử dụng biến bảng) trước khi trả về kết quả. (SV TỰ NGHĨ RA YÊU CẦU CỦA HÀM VÀ VIẾT HÀM GIẢI QUYẾT NÓ)

    Sau khi đã có hàm, viết câu lệnh sql khai thác hàm đó.

### Phần 3: Xây dựng Store Procedure (Kiến thức 10) 

  + Trong SQL Server có những SP có sẵn nào? nêu 1 vài system sp mà em tìm hiểu được, giải thích cách dùng chúng.

  + Viết 01 Store Procedure đơn giản để thực hiện lệnh INSERT hoặc UPDATE dữ liệu, có kiểm tra điều kiện logic (SV TỰ NGHĨ RA YÊU CẦU CỦA SP VÀ VIẾT SP GIẢI QUYẾT NÓ)

  + Viết 01 Store Procedure có sử dụng tham số OUTPUT để trả về một giá trị tính toán (SV TỰ NGHĨ RA YÊU CẦU CỦA SP VÀ VIẾT SP GIẢI QUYẾT NÓ, SP NÀY CÓ DÙNG THAM SỐ LOẠI OUTPUT)

  + Viết 01 Store Procedure trả về một tập kết quả (Result set) từ lệnh SELECT sau khi đã join nhiều bảng. (SV TỰ NGHĨ RA YÊU CẦU CỦA SP VÀ VIẾT SP GIẢI QUYẾT NÓ)

### Phần 4: Trigger và Xử lý logic nghiệp vụ (Kiến thức 11)

  + Viết 01 Trigger để tự động làm gì đó tại 1 bảng B khi mà dữ liệu thay đổi dữ liệu ở bảng A. Logic giải quyết do sv tự nghĩ ra, sao cho thực tế và thuyết phục.

  + Thử viết Trigger cho Bảng A : Khi insert thì cập nhật dữ liệu vào bảng B; sau đó viết trigger cho bảng B để khi B được cập nhật thì cập nhật sang bảng A : Quan sát các thông báo (nếu có) của hệ thống, giải thích các thông báo đó (nếu có). Đưa ra nhật xét cuối cùng về tình trạng này.

### Phần 5: Cursor và Duyệt dữ liệu (Kiến thức 11)

  + Viết một đoạn script sử dụng CURSOR để duyệt qua danh sách của 1 câu lệnh SQL dạng SELECT, duyệt qua từng bản ghi, xử lý riêng từng bản ghi (THEO LOGIC SV TỰ ĐẶT RA: SAO CHO HỢP LÝ VÀ THUYẾT PHỤC)

  + Tìm cách không sử dụng CURSOR để giải quyết bài toán mà em đã dùng CURSOR mới giải quyết được ở trên. thử so sánh tốc độ giữa có dùng cursor và không dùng cursor (nếu cùng kết quả) thì thời gian xử lý cái nào nhanh hơn, cần ảnh chụp màn hình minh chứng.

  + Nếu vẫn tìm được cách dùng SQL để giải quyết vấn đề mà ko cần CURSOR: thử nghĩ bài toán khác, mà chỉ CURSOR mới giải quyết được, còn SQL rất khó giải quyết đc (theo logic suy nghĩ của em)

---------
### Phần 1: Thiết kế và Khởi tạo Cấu trúc Dữ liệu (Kiến thức 6, 7) 
Tạo một Database mới với tên  [QuanLyThuVien_K235480106019]. 
Tạo các bảng:


**Bảng Sách**

MaSach: PK

GiaTien: kiểu số thực (DECIMAL)

SoLuong: có ràng buộc CHECK (không âm)

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/83c44540-6696-4b09-b95f-2d28985a3e9b" />


**Bảng Phiếu Mượn**

MaPhieu: PK

MaDocGia: FK → bảng [DocGia]

MaSach: FK → bảng [Sach]

NgayTra: có CHECK (không được nhỏ hơn ngày mượn)

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/40cf6fcf-a3f0-41cf-9238-2b76b4afa7f1" />


**Bảng Độc giả**
MaDocGia: khóa chính (PK)

Dùng NVARCHAR để hỗ trợ tiếng Việt

DATE cho ngày sinh

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/30e82b01-ec8b-4d97-a28c-d7063198c106" />


