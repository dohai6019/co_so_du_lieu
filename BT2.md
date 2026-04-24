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

### Phần 2: Xây dựng Function (Kiến thức 8, 9) 

#Một vài function mà em tìm hiểu được:

String functions: xử lý chuỗi

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/3bb8ff4a-9d95-42fe-814d-76c76deebc40" />

Date/Time functions: xử lý ngày giờ

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/866cf55b-0c2f-4e1a-9516-4798a2b6632f" />

#Viết 01 Scalar Function (Hàm trả về một giá trị): Đưa ra 1 logic cho cơ sở dữ liệu của em, mà cần dùng đến function này. 

**Bài toán**

 Tính số ngày mượn sách thực tế

Nếu chưa trả (NgayTra = NULL) thì tính đến ngày hiện tại

Nếu đã trả → tính từ NgayMuon đến NgayTra

 Ý nghĩa:

Dùng để thống kê thời gian mượn

Phục vụ tính tiền phạt, báo cáo,...

Function tính số ngày mượn sách thực tế:

Nếu chưa trả (NgayTra = NULL) → tính đến ngày hiện tại

Nếu đã trả → tính từ NgayMuon → NgayTra

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/c75498f1-fb45-452a-8936-723561c19db6" />

kết quả
<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/cdb7678e-879a-4055-ba5d-f8e30da047ae" />

Đây là Scalar Function vì:

 Trả về 1 giá trị duy nhất (INT)
 
Có xử lý logic:

Nếu chưa trả → dùng GETDATE()

Nếu đã trả → dùng NgayTra

#Viết 01 Inline Table-Valued Function: Trả về danh sách các bản ghi theo một điều kiện lọc cụ thể

**Bài toán**

 Lấy danh sách các phiếu mượn của một độc giả cụ thể

Nhập vào: MaDocGia

Trả về: danh sách các phiếu mượn của người đó

 Ý nghĩa:

Xem lịch sử mượn sách

Phục vụ thống kê theo người

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/3e57477f-3260-4c7a-a2df-a5aed1c21fdb" />

Đây là Inline Table-Valued Function vì:

Trả về bảng (TABLE)

Không dùng BEGIN...END

Chỉ chứa 1 câu SELECT

Có tham số:

@MaDocGia → giúp lọc dữ liệu linh hoạt

#Viết 01 Multi-statement Table-Valued Function: Thực hiện xử lý logic phức tạp bên trong (có sử dụng biến bảng) trước khi trả về kết quả.

**Bài toán**

 Lấy danh sách phiếu mượn + phân loại trạng thái

Phân loại:

Đang mượn → chưa trả (NgayTra IS NULL)

Đã trả → đã có ngày trả

Quá hạn → mượn quá 7 ngày

 Có thêm:

Số ngày mượn

Tiền phạt (5000đ/ngày nếu quá hạn)

Lấy danh sách phiếu mượn + phân loại trạng thái

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/94973603-5dd8-4166-8c6d-8692c5df2a0e" />

Đây là Multi-statement Table-Valued Function vì:

Có BEGIN...END

Có biến bảng @Result

Có nhiều bước xử lý logic (CASE, tính toán)

Xử lý:

Tính số ngày mượn

Phân loại trạng thái

Tính tiền phạt

### Phần 3: Xây dựng Store Procedure (Kiến thức 10) 

#Một số System SP tiêu biểu:

1. sp_help

   <img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/406c4c6b-3340-4a01-8eb4-ec50deb618a8" />

Hiển thị:

Danh sách cột

Kiểu dữ liệu

Khóa chính (PK)

Ràng buộc

2. sp_helptext

   <img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/e4fa87ee-0bb5-4cce-96ee-039a7a9f3f8e" />

Hiển thị toàn bộ code đã viết

Dùng khi:

Quên code

Muốn kiểm tra lại logic   

#Viết 01 Store Procedure đơn giản để thực hiện lệnh INSERT hoặc UPDATE dữ liệu, có kiểm tra điều kiện logic 

**Bài toán**

 Thêm sách mới vào bảng [Sach], nhưng:

 Không được trùng MaSach
 
 SoLuong phải ≥ 0
 
 GiaTien phải > 0

 Nếu sai thì báo lỗi
 
 Nếu đúng thì cho phép INSERT

Thêm sách "Mạng máy tính"

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/17ef935f-1683-4f6d-92ae-9141b9d0e9ad" />

sách đã bị trùng

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/94143df9-7651-4e9c-898c-5f0a46a81a09" />

Danh sách đã được thêm

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/1c5877e0-86fd-4e6a-8731-3a637ba0705f" />

#Viết 01 Store Procedure có sử dụng tham số OUTPUT để trả về một giá trị tính toán 

**Bài toán**

Tính tổng tiền phạt của một độc giả.

Input: @MaDocGia

Output: @TongTienPhat

Logic:

Mỗi phiếu mượn:

Quá 7 ngày thì phạt 5000đ/ngày

Cộng tất cả lại

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/3f7fd2a4-29a3-43ce-9136-e5d703a4f346" />

Store Procedure có tham số:

Input: @MaDocGia

Output: @TongTienPhat

Dùng OUTPUT để:

Trả về giá trị tính toán ra ngoài

Có sử dụng:

SUM

CASE

DATEDIFF

#Viết 01 Store Procedure trả về một tập kết quả (Result set) từ lệnh SELECT sau khi đã join nhiều bảng.

**Bài toán**

Hiển thị danh sách mượn sách chi tiết, gồm: Mã phiếu,Tên độc giả,Tên sách,Ngày mượn,Ngày trả,Trạng thái (Đã trả / Đang mượn / Quá hạn)

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/2e06c170-b164-4bbd-989b-71dfabbb131c" />

Store Procedure này:

Không dùng OUTPUT

Trả về dữ liệu bằng SELECT

Có sử dụng:

JOIN 3 bảng:

[PhieuMuon]

[DocGia]

[Sach]

CASE để xử lý logic trạng thái

Kết quả trả về là:

 Một tập bản ghi (Result Set)

### Phần 4: Trigger và Xử lý logic nghiệp vụ (Kiến thức 11)

#Viết 01 Trigger để tự động làm gì đó tại 1 bảng B khi mà dữ liệu thay đổi dữ liệu ở bảng A. Logic giải quyết do sv tự nghĩ ra, sao cho thực tế và thuyết phục.

**Bài toán**

 Khi thêm dữ liệu vào bảng [PhieuMuon] (có người mượn sách)
- hệ thống phải tự động giảm số lượng sách trong bảng [Sach]

 Logic thực tế:

Mỗi lần mượn 1 cuốn → số lượng giảm 1

Nếu hết sách - không cho mượn

**Trường hợp hợp lệ**

<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/8ab1c0a2-d049-4b9e-928e-f37e69fad24b" />

**Trường hợp hết sách**

<img width="1917" height="1080" alt="image" src="https://github.com/user-attachments/assets/ed2f01bb-733e-4ce3-8cd4-3110533f65a2" />

Trigger này được tạo trên bảng [PhieuMuon]

Chạy khi có lệnh INSERT (có người mượn sách)

Sử dụng bảng tạm inserted để lấy dữ liệu vừa thêm

Kiểm tra sách còn không

Nếu hết → hủy giao dịch (ROLLBACK)

Nếu còn → giảm số lượng sách

#Thử viết Trigger cho Bảng A : Khi insert thì cập nhật dữ liệu vào bảng B; sau đó viết trigger cho bảng B để khi B được cập nhật thì cập nhật sang bảng A : Quan sát các thông báo (nếu có) của hệ thống, giải thích các thông báo đó (nếu có). Đưa ra nhật xét cuối cùng về tình trạng này.

**Bài toán**

Bảng A: [DocGia]

Bảng B: [Sach]

Yêu cầu:

Insert vào A → update B

Update B → update lại A

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/f07b6c33-0daa-4c1e-9c54-acf38b483ee9" />

Trigger hai chiều giữa các bảng là thiết kế không an toàn vì có thể gây ra vòng lặp vô hạn. Trong trường hợp này không xảy ra lỗi do câu lệnh UPDATE không làm thay đổi dữ liệu, nhưng nếu thay đổi thực sự thì hệ thống sẽ báo lỗi do vượt quá mức lồng trigger.

### Phần 5: Cursor và Duyệt dữ liệu (Kiến thức 11)

#Viết một đoạn script sử dụng CURSOR để duyệt qua danh sách của 1 câu lệnh SQL dạng SELECT, duyệt qua từng bản ghi, xử lý riêng từng bản ghi

<img width="1920" height="1078" alt="image" src="https://github.com/user-attachments/assets/f910e165-49d7-4733-bee7-d79b8bf85f8b" />

CURSOR được dùng để:

Duyệt từng bản ghi trong bảng [PhieuMuon]

Với mỗi dòng:

Kiểm tra trạng thái mượn

Tính toán tiền phạt nếu cần

In kết quả riêng cho từng phiếu

 #Tìm cách không sử dụng CURSOR để giải quyết bài toán mà em đã dùng CURSOR mới giải quyết được ở trên. thử so sánh tốc độ giữa có dùng cursor và không dùng cursor (nếu cùng kết quả) thì thời gian xử lý cái nào nhanh hơn, cần ảnh chụp màn hình minh chứng.

Không sử dụng CURSOR

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/70c736fd-4800-494e-90b0-8a14f4e98143" />

So sánh

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/5853d869-fe91-4a5a-a260-8392ddeea2a1" />

**Kết luận**

Không dùng CURSOR:

 Nhanh hơn rõ rệt
 
 Tối ưu hơn
 
 Nên dùng trong thực tế
 
CURSOR:

 Chậm do xử lý từng dòng
 
 Chỉ dùng khi logic phức tạp không thể viết bằng SELECT

#Nếu vẫn tìm được cách dùng SQL để giải quyết vấn đề mà ko cần CURSOR: thử nghĩ bài toán khác, mà chỉ CURSOR mới giải quyết được, còn SQL rất khó giải quyết đc (theo logic suy nghĩ của em)

 Bài toán (chỉ CURSOR xử lý hợp lý)
 Ý tưởng

 Gửi cảnh báo cho từng độc giả nếu tổng tiền phạt vượt ngưỡng, đồng thời:

Với mỗi độc giả:

Tính tổng tiền phạt

Nếu > 50,000 → “gửi thông báo riêng”

Nội dung thông báo khác nhau theo từng người

 Đây là dạng:

Xử lý từng đối tượng riêng biệt

Có thể mở rộng: gửi email, ghi log, gọi API.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/4fc5d8d2-16eb-4d74-a35f-4ece701bcdaf" />

không sử dụng cursor

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/ae2f1bfc-ddde-4cf3-bd1b-d412a9a1334e" />

Kết luận 

SQL thuần:

Phù hợp xử lý theo tập dữ liệu

Nhanh và tối ưu

CURSOR:

Phù hợp khi cần xử lý từng dòng riêng biệt

Thực hiện logic phức tạp theo từng đối tượng

Mặc dù nhiều bài toán có thể thay thế CURSOR bằng SQL thuần, nhưng trong các trường hợp cần xử lý riêng từng bản ghi với logic khác nhau hoặc tương tác bên ngoài, CURSOR là công cụ cần thiết và phù hợp hơn.
