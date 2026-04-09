# Bài tập môn Hệ quản trị cơ sở dữ liệu-TEE560, Lớp: 59KMT

## YÊU CẦU BÀI TẬP #

1. Download và cài đặt SQL Server 2025, phiên bản Developer

   Link tải: https://www.microsoft.com/vi-vn/sql-server/sql-server-downloads 

   Chọn phiên bản *SQL Server 2025 Developer*
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/3d00eae9-794f-4f25-8a06-dd5cc173611e" />

Chọn Download Media
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/9d8b86d6-e993-4113-ba74-cf8b0d735c88" />

Chọn Download khi đó sẽ hiện một ổ đĩa như sau:
<img width="755" height="29" alt="image" src="https://github.com/user-attachments/assets/dbdf07c8-80a3-4381-9874-504c43c9ed24" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/38033b3a-dc33-4e82-af42-823ce60fb5ab" />

Chọn setup để cài đặt:
<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/e47a76a8-117a-4abd-96cf-21746d81ac8d" />

Chọn Installation và Chọn "New SQL ..."

   Không chọn Azure (nặng, ko dùng đến), các tính năng mở rộng khác (feature) chọn tất cả   
<img width="1006" height="885" alt="image" src="https://github.com/user-attachments/assets/7c3794ba-ba35-4be4-b0ec-c013467d9183" />

<img width="1006" height="885" alt="image" src="https://github.com/user-attachments/assets/b1124056-5ca5-4319-8f46-0a767c9b4c16" />

   Cài đặt với 2 kiểu login (Mixed Mode): Windows Authentication (nhớ **Add Current User**) và SQL Server Authentication (username mặc định là **sa**, chỉ cần nhập mật khẩu **123** , nhớ nhập 2 chỗ: Enter password và Confirm password)
<img width="1006" height="885" alt="image" src="https://github.com/user-attachments/assets/1d130c3b-45b7-49c9-bf55-10a630009867" />

Đã cài đặt với 2 kiểu login

2. Cấu hình cho SQL Server làm việc ở cổng động (Dynamic Port), TCP: enable+active yes cho 127.0.0.1, chọn cổng động là 3xxxx với xxxx là **4 số cuối của mã số sv**, (nếu cổng này đã mở sẵn trước đó bởi 1 ứng dụng khác thì chọn cổng là 4xxxx hoặc 5xxxx)
<img width="515" height="630" alt="image" src="https://github.com/user-attachments/assets/334fcfc6-4b61-45a6-a110-bda4136dc80a" />

3. Kiểm tra xem service SQL Server có đang running và mở đúng cổng đã chọn hay không?

   Sử dụng lệnh trên cmd: *netstat -ano | findstr LISTENING* để liệt kê các cổng mà máy tính đang mở,

   Nếu thấy dòng: **TCP    0.0.0.0:xxxxx**  với xxxxx là cổng đã chọn ở bước 2 là OK.
<img width="1103" height="639" alt="image" src="https://github.com/user-attachments/assets/0e26e7a6-8c35-4abb-928c-42566406e83f" />

Đã mở cổng
4. Cài đặt SQL Server Management Studio

   Link tải SSMS: https://learn.microsoft.com/en-us/ssms/install/install
<img width="1920" height="1080" alt="Screenshot 2026-04-09 054017" src="https://github.com/user-attachments/assets/6f4143a5-2d13-4517-a514-d3b4ad58b6d7" />

5. Chạy phần mềm ssms để Đăng nhập vào SQL Server bằng 2 cách: Windows Authentication và SQL Server Authentication.

   Servername: localhost,xxxxx  (với xxxxx là cổng đã chọn ở bước 2)
<img width="1920" height="1080" alt="Screenshot 2026-04-09 054017" src="https://github.com/user-attachments/assets/6f4143a5-2d13-4517-a514-d3b4ad58b6d7" />

6. Sử dụng giao diện đồ hoạ của ssms: Tạo cơ sở dữ liệu mới (create database) với tên tuỳ ý, chọn Path (nơi lưu trữ db) cho file lưu dữ liệu và file lưu log ở ổ đĩa khác với ổ C. mở path đã chọn xem 2 file đã tạo ra.

<img width="942" height="811" alt="image" src="https://github.com/user-attachments/assets/61fe7337-bc7e-4443-8b33-a9eaf78f5e0c" />

7. Sử dụng giao diện đồ hoạ của ssms: Tạo bảng dữ liệu (create and design table) với tên bảng tuỳ ý, có các trường dữ liệu phù hợp với dữ liệu của file [data mẫu (CSV)](./svtnut.csv?raw=true), với Khoá chính (Primary Key) là trường **masv**
<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/20eab05d-3254-4eeb-89ed-ece8cd1ce062" />

8. Sử dụng giao diện đồ hoạ của ssms: Tìm cách import dữ liệu từ file mẫu vào trong bảng vừa tạo.
<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/cfa13bbb-a328-4c58-b687-3c26192872aa" />

Sử dụng code để import dữ liệu
9. Mở cửa sổ mới để gõ lệnh trong ssms: GÕ lệnh để kiểm tra xem số dòng của bảng dữ liệu sau khi import, kết quả ok sẽ khoảng 12020 dòng.
<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/83f4bef5-c46c-45d8-8b6e-091148d3d999" />

10. Trong cửa sổ mới để gõ lệnh: Gõ lệnh để thêm (insert) 1 row vào bảng, với dữ liệu là thông tin cá nhân của sv đang làm bài (mỗi sv sẽ luôn khác nhau ở bước này). 
<img width="1920" height="1030" alt="image" src="https://github.com/user-attachments/assets/35f4583d-3cdb-4381-9b94-d2349dfe8332" />

11. Trong cửa sổ mới để gõ lệnh: Gõ lệnh để cập nhật(update) trường noisinh thành 'Sao Hoả' cho những dòng có noisinh và diachi đều là NULL.
<img width="285" height="94" alt="image" src="https://github.com/user-attachments/assets/459632d9-1dab-4829-965e-5172e784af01" />

<img width="809" height="668" alt="image" src="https://github.com/user-attachments/assets/d364d2a7-a314-45ed-8005-bb5173b8f874" />

12. Sử dụng giao diện đồ hoạ của ssms: Tạo bảng **SaoHoa** gồm những sinh viên có nơi sinh ở 'Sao Hoả', keyword gợi ý: sử dụng 1 câu lệnh: SELECT + INTO
<img width="320" height="97" alt="image" src="https://github.com/user-attachments/assets/9d1817db-cec2-4833-9144-c0b223718822" />

<img width="1920" height="1080" alt="image" src="https://github.com/user-attachments/assets/965e0339-3db2-4e0a-926d-0f86a108acfe" />

13. Trong cửa sổ mới để gõ lệnh: Gõ lệnh xoá (delete) trong bảng **SaoHoa** những sinh viên cùng họ với em, vd em họ nguyễn thì xoá những sv họ nguyễn.
<img width="1920" height="1080" alt="Screenshot 2026-04-09 062802" src="https://github.com/user-attachments/assets/9fbd2141-5984-408c-bff6-1f39faba9cac" />

Câu lệnh: DELETE FROM SaoHoa WHERE hotensv LIKE N'Đỗ%';
<img width="1920" height="1080" alt="Screenshot 2026-04-09 062844" src="https://github.com/user-attachments/assets/0c74521c-8213-4c6c-9ea7-fc2f343f5952" />

14. Sử dụng giao diện đồ hoạ của ssms: Xuất toàn bộ kết quả của các bước 6,7,8,9,10,11,12,13 ra file **dulieu.sql** , keyword gợi ý: sử dụng tính năng GEN SCRIPT struct+data cho database
<img width="952" height="826" alt="Screenshot 2026-04-09 063114" src="https://github.com/user-attachments/assets/1d21ff58-8ae8-4d1b-a383-78aea58f3a3d" />

Đã xuất thành công
15. Sử dụng giao diện đồ hoạ của ssms: Xoá csdl đã tạo, sau khi xoá thành công, kiểm tra tại path (path chọn ở bước 6) xem còn tồn tại 2 file của bước 6 không?
<img width="1407" height="742" alt="Screenshot 2026-04-09 063409" src="https://github.com/user-attachments/assets/4daff045-c7d7-4f33-884a-41a7080075c8" />

Sau khi xóa database sẽ không còn tồn tại database nữa
16. Tạo cửa sổ mới để gõ lệnh: mở file **dulieu.sql** của bước 14, chạy toàn bộ các lệnh này. REFRESH lại cây liệt kê các database => kiểm chứng kết quả được tạo ra tương đương với các bước 6,7,8,9,10,11,12,13.
<img width="1920" height="1080" alt="Screenshot 2026-04-09 063603" src="https://github.com/user-attachments/assets/400650fc-2882-4256-864a-6d9e9abb3564" />

Tạo thành công trở lại các dữ liệu
17. upload file **dulieu.sql** lên github repository của em (repository mà em đang edit file README.md)
