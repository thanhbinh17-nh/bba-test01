# GIT - DOCUMENT-1
### 1. Git init
- Dùng để khởi tạo repo local, Thực hiện duy nhất một lần khi bắt đầu một dự án mới hoàn toàn trên máy tính
- Khi chạy lệnh này, Git sẽ tạo ra một thư mục ẩn tên là .git trong thư mục hiện tại. Thư mục này chứa toàn bộ cấu hình, lịch sử và siêu dữ liệu (metadata) cần thiết để Git theo dõi các thay đổi.
- Ý nghĩa: Dùng để biến một thư mục thông thường trên máy tính thành một kho lưu trữ Git mới (Local Git Repository).
### 2. Git add
- git add <file name>, git add .,: dùng để đưa file từ working directory sang staging area
- git add <file name>: add 1 file cụ thể
- git add .: add tất cả các file trong thư mục hiện tại
### 3. Git commit -m"message"
 - Lưu chính thức các file đang nằm trong Staging Area thành bản ghi vĩnh viễn trên kho lưu trữ Git ở máy local.
 ### 4. Git remote add origin <'url'>
- Kết nối Git Repository ở máy local với Github của mình
- Thực hiện duy nhất một lần khi bắt đầu một dự án mới hoàn toàn trên máy tính

### 5. Git push -u origin main
- Đẩy toàn bộ các bản commit từ máy tính local lên GitHub.

### **VÍ DỤ TRẠNG THÁI FILE** 

a. Sau khi tạo 3 file1,2,3 --> 3 file thuộc working directory, Git chưa quản lý thư mục này nên chúng chưa được theo dõi (Untracked).

b. Sau khi chạy lệnh git init: Git đã khởi tạo kho lưu trữ (.git). Git bắt đầu nhận diện thấy sự xuất hiện của 3 file này nhưng trạng thái của chúng vẫn là Untracked vì chưa dùng lệnh add 
--> 3 file thuộc working directory.

c. git commit -m"init project" ==> Không có gì xảy ra vì chưa có file nào được ad, chưa có gì để commit.
--> 3 file thuộc working directory.

d. git add file1 --> add file 1 vào staging area, file2,3 vẫn thuộc working directory

e. git commit -m"add file1" --> file1 được lưu chính thức vào Local Repository, file2,3 vẫn thuộc working directory

f. git commit -m"add file" --> Không có gì xảy ra vì staging are trống, file1 đã commit rồi còn file2,3 chưa được add, vùng staging area không có gì để commit.
 --> file1 đã được lưu chính thức vào Local Repository, file2,3 vẫn thuộc working directory