# Lý thuyết, tính toán về tụ điện
Tụ điện là một linh kiện điện tử thụ động có khả năng tích trữ và phóng điện
# Cấu tạo
Gồm 3 phần chính:

Hai bản dẫn (plates) nằm ở 2 bên: thường làm bằng nhôm, đồng, thiếc, v.v.

Lớp điện môi (dielectric) nằm ở giữa: cách điện, có thể là không khí, mica, giấy, gốm, tantalum, nhôm oxit,...

Vỏ bảo vệ (housing) bao bọc xung quanh: giữ cấu trúc cơ khí, tránh ẩm và hư hại.

Kí hiệu: -| |-

# Nguyên lí hoạt động
Khi hai bản tụ được nối vào nguồn điện, bản dương tích điện dương (+), bản âm tích điện âm (−). Giữa hai bản xuất hiện điện trường -> năng lượng được lưu trữ trong điện trường này. Khi ngắt nguồn, tụ vẫn giữ điện trong một khoảng thời gian và có thể phóng điện khi ta nối vào mạch khác.
# Công thức liên quan đến tụ
1. Điện dung của tụ: là khả năng tích điện của tụ theo cấu tạo `C = epxilon x (A/d)` đơn vị là Fara (F)

Trong đó:
  - epxilon là hằng số điện môi
  - A là diện tích 2 bản tụ
  - d là khoảng cách của 2 bản tụ

2. Điện tích của tụ: là lượng điện mà tụ đang lưu trữ trên hai bản của nó tại một thời điểm nhất định `Q = C.U` đơn vị là Coulomb
T
Trong đó:
  - Q là điện tích
  - C là điện dung = Q/U
  - U là hiệu điện thế

3. Thời gian nạp đầy của tụ: là khoảng thời gian để tụ tích trữ đầy điện, ta có công thức được chúng minh: `t = 5.R.C`

4. Thời gian xã hết điện trong tụ = Thời gian nạp = `5.R.C`

5. Ghép tụ nối tiếp: Điện áp chính là điện áp tổng
```
U = U1 + U2
1/C = 1/C1 + 1/C2
Q = Q1 = 
```  

7. Ghép tụ song song: Ghép chung đầu nên cùng điện áp 
```
U = U1 = U2
C = C1 + C2
Q = U.(C1 + C2) 
```
   
# Ứng dụng của tụ
- Phóng điện, tích trữ điện
- Lọc nguồn (power filter):	Làm mịn điện áp DC sau chỉnh lưu
- Ghép tín hiệu (coupling):	Cho tín hiệu AC đi qua, chặn DC
- Tách tín hiệu (decoupling):	Giảm nhiễu nguồn trong mạch số
- Dao động (oscillator):	Cùng cuộn cảm tạo mạch LC
- Trì hoãn (delay):	Tụ nạp/phóng tạo trễ trong mạch RC
- Khởi động động cơ:	Dùng tụ khởi động pha phụ
