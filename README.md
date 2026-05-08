# BÀI TẬP VỀ NHÀ 03: THIẾT KẾ VÀ CÀI ĐẶT CSDL QUẢN LÝ CẦM ĐỒ 

# Môn học: Hệ quản trị CSDL. Lớp 59KMT. GV: Đỗ Duy Cốp

## HỌ VÀ TÊN: ĐỖ NGỌC HẢI

## MSSV: K235480106019

## LỚP: K59KMT.K01

### Nhiệm vụ 1: Thiết kế CSDL 

Vẽ sơ đồ ERD: thể hiện rõ thực thể, thuộc tính, khóa chính, khóa ngoại. 

Chuyển sơ đồ thành các bảng (Lưu ý chuẩn hóa tối thiểu mức 3NF). 

### Hệ thống quản lý cầm cố/thế chấp cần xử lý:

 Quản lý khách hàng
 
 Quản lý hợp đồng vay
 
 Một hợp đồng có nhiều tài sản thế chấp
 
 Theo dõi biến động khoản nợ theo thời gian
 
 Theo dõi trạng thái hợp đồng
 
 Tính lãi đơn và lãi kép
 
 Trả nợ từng phần
 
 Thanh lý tài sản khi quá hạn

### Để đạt chuẩn hóa tối thiểu 3NF, cần tách:

 Thông tin khách hàng
 
 Thông tin hợp đồng
 
 Thông tin tài sản
 
 Quan hệ hợp đồng và tài sản
 
 Lịch sử biến động nợ/trạng thái

<img width="1920" height="1075" alt="Screenshot 2026-05-08 165230" src="https://github.com/user-attachments/assets/10c680ca-21a7-42ad-9543-2ec5ec3d4db0" />

### sơ đồ ERD

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/b7538341-4248-426e-8495-392c4f52155f" />

### Nhiệm vụ 2: Cài đặt SQL (Yêu cầu viết Scripts) 

### Event 1: Đăng ký hợp đồng mới (Vay tiền) 

Viết Store Procedure tiếp nhận hợp đồng: Lưu thông tin khách hàng, danh sách tài sản 

(kèm giá trị định giá), số tiền vay gốc và thiết lập 2 mốc Deadline1, Deadline2. 

Tạo Store Procedure tiếp nhận hợp đồng

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/440a9282-e23c-4f64-afc2-15b0b4f61581" />

sau khi đã tạo Store Procedure xong, test dữ liệu và ta được:

<img width="1920" height="1080" alt="Screenshot 2026-05-08 211217" src="https://github.com/user-attachments/assets/1f380f24-d93d-40ed-9d0c-684f50ea3187" />

<img width="1920" height="1080" alt="Screenshot 2026-05-08 211251" src="https://github.com/user-attachments/assets/7f51ad02-cbbf-47c6-af78-a3b57b81c579" />

### Event 2: Tính toán công nợ thời gian thực 

Viết một Function fn_CalcMoneyTransaction(TransactionID, TargetDate) để tính số tiền phải trả của TransactionID này cho đến ngày TargetDate 

Viết một Function fn_CalcMoneyContract(ContractID, TargetDate) để tính tổng số tiền khách(ContractID) phải trả (Gốc + Lãi đơn + Lãi kép) tính đến ngày TargetDate. 

### Function fn_CalcMoneyTransaction:

Function này dùng để tính số tiền phải trả của một giao dịch tại thời điểm TargetDate.

### Ví dụ:

giao dịch vay tiền

giao dịch cộng lãi

giao dịch gia hạn

giao dịch quá hạn

Function sẽ tính:

tiền gốc

lãi phát sinh theo số ngày

### Function này giúp:

tính tiền phát sinh của từng giao dịch

theo dõi lãi theo thời gian thực

hỗ trợ quản lý công nợ chính xác

### Function fn_CalcMoneyContract:

Function này dùng để tính tổng số tiền khách hàng phải trả cho toàn bộ hợp đồng.

### bao gồm

tiền gốc

lãi đơn

lãi kép

Hai Function trên giúp hệ thống:

tính công nợ tự động

theo dõi khoản vay theo thời gian thực

hỗ trợ cảnh báo quá hạn

hỗ trợ quản lý lãi suất

giảm sai sót khi tính toán thủ công

Việc sử dụng Function trong SQL Server giúp hệ thống xử lý nghiệp vụ tài chính tự động và chính xác hơn.
Function fn_CalcMoneyTransaction hỗ trợ tính công nợ cho từng giao dịch, còn fn_CalcMoneyContract hỗ trợ tính tổng công nợ của hợp đồng bao gồm cả lãi đơn và lãi kép.

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e4657b91-f9ad-4849-a230-9c5ef16a7f3b" />

### Event 3: Xử lý trả nợ và hoàn trả tài sản 

Viết Viết Store Procedure xử lý khi khách mang tiền đến: 

Nếu tài sản đã bị thanh lý (sau Deadline 2 và có cờ IsSold): Thông báo không thu tiền, không trả đồ. 

Nếu tài sản chưa bị thanh lý: Tính tổng nợ, trừ số tiền khách trả vào hệ thống. Nếu trả hết tiền, trả hết đồ và cập nhật trạng thái hợp đồng thành “Đã thanh toán đủ”; Nếu chưa trả hết tiền gốc+lãi: cập nhật trạng thái hợp đồng thành “Đang trả góp”, ghi nhận vào LOG số tiền đã trả, và số tiền còn nợ. 

Đưa ra danh sách gợi ý trả lại cho khách hàng này dựa trên điều kiện:  
Giá trị tài sản còn lại >= Dư nợ còn lại. 

sau khi đã tạo và test kết quả hiển thị:

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/2db408e6-74f4-496e-8fe3-ebe5a17df58b" />

test bảng hiển thị khách hàng đã trả nợ và còn nợ

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/245ec40b-65b1-426c-998c-b9e7edf10021" />

Procedure SP_TRA_NO giúp tự động hóa quy trình xử lý trả nợ trong hệ thống cầm đồ.

Hệ thống có thể:

kiểm soát công nợ

xử lý thanh toán

cập nhật trạng thái hợp đồng

quản lý tài sản thế chấp

một cách chính xác và an toàn hơn so với xử lý thủ công.

### Event 4: Truy vấn danh sách nợ xấu (Nợ khó đòi) 

Xuất danh sách các khách hàng đã quá Deadline 1 mà chưa thanh toán. 

Yêu cầu các cột: Tên KH, Số điện thoại, Số tiền vay gốc, Số ngày quá hạn, Tổng tiền phải trả hiện tại (đến ngày hiện tại), Tổng số tiền phải trả sau 1 tháng nữa. 

Chức năng này dùng để thống kê danh sách khách hàng có nguy cơ trở thành nợ xấu hoặc đã quá hạn thanh toán.

Hệ thống sẽ hiển thị:

tên khách hàng

số điện thoại

số tiền vay gốc

số ngày quá hạn

tổng số tiền phải trả hiện tại

tổng số tiền phải trả sau 1 tháng nữa

Nhờ đó nhân viên có thể:

theo dõi công nợ

nhắc khách thanh toán

đánh giá khả năng thu hồi nợ

 <img width="1916" height="1080" alt="image" src="https://github.com/user-attachments/assets/a5f76e5c-bc2c-402d-b743-1edcfb693496" />

 Chức năng này giúp:

quản lý danh sách nợ khó đòi

theo dõi khách hàng quá hạn

hỗ trợ nhắc nợ

đánh giá rủi ro tài chính

hỗ trợ quyết định thanh lý tài sản

Event 4 giúp hệ thống quản lý cầm đồ theo dõi các khoản vay quá hạn một cách tự động và hiệu quả.

Việc sử dụng Function và View giúp truy vấn dữ liệu nhanh hơn, dễ tái sử dụng và thuận tiện cho việc quản lý công nợ trong thực tế.

