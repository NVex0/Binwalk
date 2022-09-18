# Binwalk

Như tiêu đề của challenge thôi, sử dụng binwalk để giải.
Binwalk dùng để extract file được giấu trong 1 file....đại loại thế.

Với ảnh đã cho, sử dụng:

`binwalk -D".*" PurpleThing.png`

Vì là ảnh PNG mà lúc tải xuống nó đặt extension là JPEG, nhìn ngứa mắt nên mình đổi lại :D

options của binwalk bạn có thể xem với `binwalk -h` , như cái trên mình dùng là extract mọi đuôi có thể trong file ra.

Với Directory mới vừa được tạo ra khi dùng binwalk, vào bên trong Directory đó, thấy có filename là `25795`, mở nó ra và được Flag.

Hoặc muốn hiểu rõ hơn thì bạn dùng 1 công cụ để edit hexdata của nó ý, ví dụ mình hay dùng `bless`. Format của 1 ảnh PNG bắt đầu bằng PNG và kết thúc bằng IEND.B'. Nhưng trong ảnh này thì có tới 2 cái đuôi IEND. khi mình tìm với text. Tức là có 1 cái ảnh PNG khác được nhét thêm vào. Và bạn chỉ Copy cái đầu .PNG -> IEND.B của cái ảnh thêm sang file khác là được.
