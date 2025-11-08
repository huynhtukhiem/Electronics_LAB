# Chuyển đổi AC thành DC bằng mạch cầu chỉnh lưu 
- Mục đích: Biến nguồn điện AC 220V dân dụng ở hộ gia đình thành nguồn điện DC 5V sử dụng cho các mục đích riêng
- Nâng cao hơn: Có thể tùy chỉnh điện áp đầu ra DC theo ý muốn bằng IC LM317
- Mô phỏng trước trên Proteus: 
  - Link youtube:
  - Link tiktok:

# Linh kiện cần sử dụng
- Nguồn AC
- Biến áp
- 4 diode hoặc cầu diode
- IC 7805, datasheet: ....
- Tụ hóa
- Tụ gốm
- IC LM317 (Nâng cao)

# Nguyên lý hoạt động

# Sơ đồ mắc mạch
Hình ảnh

# Tính toán các thông số để chọn linh kiện
Mục tiêu: Chuyển 220V AC thành 5V DC
- Biến áp
```
Trước hết ta biết điện áp sơ cấp sẽ là 220V
Vậy cần tính điện áp thứ cấp của biến áp

Theo datasheet của IC 7805 thì V_in >= 7V (điện áp vào IC tối thiểu là 7V) và theo sơ đồ mắc mạch thì sau khi chỉnh lưu và lọc thì điện áp đầu ra phải lớn hơn 7V để cấp cho IC.

Ta rút được công thức sau: V_DC = 1.414 x V_AC - 1.4
Trong đó:
  1.414 x V_AC là điện áp cực đại của AC (điện áp DC sau khi lọc sẽ xấp xỉ bằng điện áp đỉnh của sóng AC)
  1.4 là sụt áp của 2 diode dẫn mỗi nữa chu kỳ

Vì V_DC cần tìm >= 7 nên ta có:
1.414 x V_AC -1.4 >= 7
<=> V_AC xấp xỉ 5.94V làm tròn thành 6V

Vậy điện áp thứ cấp của biến áp theo lý thuyết là 6V, tuy nhiên theo thị trường thì giá trị có thể là 6V, 7.5V, 9V, 11V,.....
Với 6V => lọc ra 7.1V  hơi sát
Với 7.5V => lọc ra 9.2V hợp lí, nhưng chỗ mình không có bán loại này
Với 9V => lọc ra 11.3V hợp lí, bán nhiều loại biến áp này

Dòng điện mình sẽ chọn là 0.5A

=> Kết luận: điện áp sơ cấp: 220V, điện áp thứ cấp 9V, dòng: 0.5A
```
- Tụ hóa
```
Vì tụ hóa nằm sau 4 diode nên theo các nguồn tin, ta có công thức:
C = I_tải/2f x denta_V
Trong đó:
  I_tải là dòng tải, ta chọn là 0.5A như trên
  f = 50Hz, tần số ở việt nam
  denta_V: mức dao động điện áp mà ta  cho phép xảy ra sau khi chỉnh, sau khi chỉnh lưu, tụ nạp khi điện áp tăng và xả khi điện áp giảm => điện áp DC không thể phẳng tuyệt đối mà hơi nhấp nhô, vậy nên denta_V là biên độ dao động đó

Nếu denta_V = 1V => V_DC dao động từ 10V - 12V
  Nếu denta_V = 2V => V_DC dao động từ 9V - 13V
=> muốn điện áp V_DC phẳng thì chọn denta_V càng nhỏ như lại cần tụ lớn hơn để điện tích duy trì điện
Vậy ta chọn denta_V = 1V

Thay số: C = I_tải/2f x denta_V
<=> C = 0.5 / 100 x 1
<=> C = 0.005F = 5000 oFara
và chọn lại tụ hóa có thông số điện dung là 4700 microFara
điện áp của tụ hóa cần lớn hơn điện áp DC là 11V nên chọn loại 16V hoặc 25V
=> Chọn tụ hóa có thông số là 4700 microFara và 25V
```

- Tụ gốm
  
| Loại tụ |	Dung lượng | Dải tần lọc tốt nhất|
|:------|:-----:|------:|
| Tụ hóa |	µF–mF |	Tốt ở tần số thấp (50–1000 Hz)|
| Tụ gốm 1 µF |	kHz–100 kHz |	Lọc nhiễu trung bình |	
| Tụ gốm 0.1 µF (100 nF) |	>100 kHz đến vài MHz	| Lọc nhiễu cao tần cực tốt |	
| Tụ gốm 10 nF | MHz–chục MHz	| Cho mạch RF, tốc độ cao	|

Chọn loại 0.1 microFara (rẻ, nhỏ, dễ kiếm)

