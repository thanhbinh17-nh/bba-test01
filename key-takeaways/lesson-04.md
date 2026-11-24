# GIT - DOCUMENT-4

### 1. Phạm vi của biến
- Block scope (khối): biến được khai báo trong cặp ngoặc nhọn
+ var: không bị giới hạn bởi cặp ngoặc nhọn
+ let/const: bị giới hạn bởi cặp ngoặc nhọn. Ra ngoài bị undefined
- Ví dụ:
if (true) {
    var varVariable = "var không có block scope";
    let letVariable = "let có block scope";
    const constVariable = "const cũng có block scope";
}

console.log(varVariable);   // OK - var không bị giới hạn bởi block
console.log(letVariable);   // Error: letVariable is not defined
console.log(constVariable); // Error: constVariable is not defined

- Function scope(hàm): biến được khai báo trong hàm
  + Cả let/var/const: ra ngoài hàm đều bị underfined

- Global (toàn cục): biến được khai báo ở dòng code tự do, không nằm trong hàm hay khối. Không bị giới hạn bởi cặp {} nào cả nên dù chưa khai báo trong hàm, trong khối if... thì vẫn dùng được bên trong hàm, trong khối.

### 2. Break và continue
2.1 Break: thoát khỏi vòng lặp ngay lập tức khi đáp ứng điều kiện
2.2 Continue: bỏ qua phần còn lại của vòng lặp hiện tại và bắt đầu lần lặp tiếp theo

### 3. For in
for (const A in person){ 
    console.log(A);
}
- vòng lặp với biến A, mỗi lần lặp sẽ lấy 1 key thuộc object person đã khai báo để gán vào biến A, vòng lặp này chạy lần lượt qua all key trong object.

 ### 4. For each
 number.forEach(function(value){   
    console.log(A);
    console.log(value);
}
- vòng lặp thực thi 1 function cho mỗi phần tử trong array. Không thể dùng break, continue

### 5. Utils function
- Utils = tiện ích
- Utils function là các hàm có sẵn của JavaScript, giúp việc code trở nên nhanh gọn hơn.
- 2 loại utils function thường sử dụng:
• String utils: các hàm xử lý chuỗi
• Array utils: các hàm xử lý mảng

5.1
- trim(): bỏ khoảng trắng 2 đầu
- trimStart(): bỏ khoảng trắng bên trái
- trimEnd(): bỏ khoảng trắng bên phải

5.2 
- console.log(str.toUpperCase()); // chuyển toàn bộ chuối str thành chữ hoa
- console.log(str.toLowerCase()); // chuyển toàn bộ chuối str thành chữ thường

5.3 
- console.log(text1.includes('Nhat')); // Kiểm tra chuỗi có chứa chuỗi con không, có phân biệt viết hoa thường

5.4 
- console.log(text2.split(' ')); // cắt chuỗi theo khoảng trắng, trả về các chuỗi con riêng biệt 
- console.log(text3.split('@')); //// cắt chuỗi theo dấu @
- console.log(date.split('-')); //// cắt chuỗi theo dấu -

5.5 
- console.log(text4.replace('Lam May','Ngoc Diep'));  // replace chuỗi bên phải thành chuỗi bên trái, replace chỉ hoạt động với chuỗi, không hoạt động với mảng

5.6 Thêm phần tử vào mảng
- Thêm vào cuối: push(<phần tử muốn thêm>)
- Thêm vào đầu: unshift(<phần tử muốn thêm>>)
- Thêm vào vị trí bất kì: splice(<vị trí (đếm từ 0)>, <số phần tử cần xoá>, <phần tử cần thêm vào>)
+ cấu trúc .splice(n, 0, x) --> ý nghĩa: check vị trí thứ n, xóa đi 0 phần tử tính từ n đổ về sau, thêm phần tử mong muốn (là x) vào trước n

5.7 Xóa phầ tử khỏi mảng 
- Xóa ở cuối: pop()
- Xóa ở đầu: shift()
- Xóa ở vị trí bất kỳ: splice(<vị trí(đếm từ 0)>, <số phần tử cần xóa>)
+ cấu trúc .splice(x,y) --> ý nghĩa: tính đến vị trí x, xóa đi y phần tử tính từ x đổ về sau.

5.8 Tìm kiếm phần tử
- Trả về phần tử đầu tiên hợp lệ - find()
- Trả về tất cả các phần tử hợp lệ - filter()

5.9
- hàm map, dùng để tạo ra mảng mới sao cho lấy mảng gốc nhân đôi các phần tử để ra phần tử của mảng mới
const so = [5, 10, 15, 25, 40];
let double = so.map(B => B*2); 

5.10 Sắp xếp
- So sánh từng cặp phần tử a và b trong mảng
- sort((a, b) => a - b)
	• a-b Trả về số âm: a đứng trước b
	• a-b Trả về số dương: b đứng trước a
	• a-b Trả về 0: giữ nguyên vị trí
    ==> dựa vào phép tính a-b để xem a và b có nên đổi chỗ không
- D.sort((a,b) => b - a);    // sxep giảm dần
  console.log(D);

- D.sort((a,b) => a - b);    // sxep tăng dần
  console.log(D);