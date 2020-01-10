# Linux system file
## Các lo hệ thống tệp Linux

`Ext`, `Ext2`, `Ext3`, `Ext4`, `JFS`, `XFS`, `BTRFS`

* `Ext` Không còn sử dụng.
* `Ext2` Hệ thống tệp Linux đầu tiên, cho phép 2T dữ liệu.
* `Ext3` Được nâng cấp từ `Ext2` được nâng cấp và có vấn đề các máy chủ không sử dụng loại tệp này vì k hỗ trợ phục hồi tệp.
* `Ext4` Nhanh hơn, cho phép các tệp lớn hơn, tốc độ nhanh.
* `JFS` Hệ thống tệp hđ tốt vs tệp nhỏ và lớn, Nhưng các tệp bị hỏng sau thời gian dài sử dụng.
* `XFS` Hệ thống tệp cũ và hđ chậm với các tệp nhỏ.
* `BTRFS` Được thực hiện bở Oracle.  Nó không ổn định như Ext trong một số distro.

__`EXT4`__ Hệ thống tệp `Linux` tốt nhất.

# Thư mục hệ thống tệp Linux

`/ bin` : Nơi lưu trữ các lệnh lõi Linux : ls, mv, cd...

`/ boot` : Nơi đặt các bộ khởi động và tập tin khởi động.

`/ dev` : DVD USB các ổ đĩa vật lý

`/ etc` : Chứa cấu hình các gói cài đặt

`/ home` : Nơi mọi người dùng sẽ có một thư mục cá nhân để đặt với /home/nrx2.

`/ lib` : Nơi thư viện của các gói cài đặt chia sẻ giữa các gói.

`/ media` : Truy cập Các thiết bị vật lý bên ngoài như DVD USB từ đây.

`/ mnt` : Dùng mount các thiết bị vật lý.

`/ opt` : Một số gói được đặt và quản lý bởi người quản lý gói.

`/ proc` : Thư mục này dành cho các quy trình đang chạy trên hệ thống. Xem thông tin quy trình hiện tại.

`/ root` : Thư mục gốc cho người dùng `root`.

`/ sbin` : giống bin, nhưng chỉ dành cho người dùng `root`.

`/ tmp` : Chứ các tệp tạm thời.

`/ usr` : Nơi các tiện ích được chia sẻ giữa người dùng trên Linux.

`/ var` : Chứa nhật ký hệ thống và dữ liệu biến khác.

`/ run` : Chứa dữ liệu thời gian chạy.