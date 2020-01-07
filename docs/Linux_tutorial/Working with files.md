# Working with files
## Tổng quan về file
---
Cây thư mục bắt đầu từ thư mục gốc ( / ).
Trong linux, Hệ thống chia làm 3 loại :
* File thông thường
* Thư mục
* File đặc biệt
```
nrx2@nrx2:~$ ls -la /
total 81
drwxr-xr-x  20 root root  4096 Jan  3 14:59 .
drwxr-xr-x  20 root root  4096 Jan  3 14:59 ..
lrwxrwxrwx   1 root root     7 Nov 25 10:02 bin -> usr/bin
drwxr-xr-x   5 root root  1024 Jan  1 08:46 boot
drwx------   2 root root  4096 Nov 25 10:07 .cache
drwxr-xr-x  20 root root  3680 Jan  7 22:02 dev
drwxr-xr-x 169 root root 12288 Jan  7 22:28 etc
drwxr-xr-x   3 root root  4096 Nov 25 10:20 home
lrwxrwxrwx   1 root root    33 Nov 25 10:02 initrd.img -> boot/initrd.img-5.2.0-kali2-amd64
lrwxrwxrwx   1 root root    33 Nov 25 10:02 initrd.img.old -> boot/initrd.img-5.2.0-kali2-amd64
lrwxrwxrwx   1 root root     7 Nov 25 10:02 lib -> usr/lib
lrwxrwxrwx   1 root root     9 Nov 25 10:02 lib32 -> usr/lib32
lrwxrwxrwx   1 root root     9 Nov 25 10:02 lib64 -> usr/lib64
lrwxrwxrwx   1 root root    10 Nov 25 10:02 libx32 -> usr/libx32
drwx------   2 root root 16384 Nov 25 10:02 lost+found
drwxr-xr-x   4 root root  4096 Nov 29 13:10 media
drwxr-xr-x   3 root root  4096 Dec  4 01:56 mnt
drwxr-xr-x   7 root root  4096 Dec 26 14:13 opt
dr-xr-xr-x 246 root root     0 Jan  7 22:01 proc
drwxr-xr-x  14 root root  4096 Dec 21 12:10 root
drwxr-xr-x  40 root root  1180 Jan  7 22:51 run
lrwxrwxrwx   1 root root     8 Nov 25 10:02 sbin -> usr/sbin
drwxr-xr-x   2 root root  4096 Dec 26 08:19 snap
drwxr-xr-x   3 root root  4096 Nov 25 10:02 srv
dr-xr-xr-x  13 root root     0 Jan  7 22:01 sys
drwxrwxrwt  21 root root  4096 Jan  7 23:32 tmp
drwxr-xr-x  15 root root  4096 Nov 25 10:06 usr
drwxr-xr-x  13 root root  4096 Dec 26 08:15 var
lrwxrwxrwx   1 root root    30 Nov 25 10:07 vmlinuz -> boot/vmlinuz-5.2.0-kali2-amd64
lrwxrwxrwx   1 root root    30 Nov 25 10:07 vmlinuz.old -> boot/vmlinuz-5.2.0-kali2-amd64
nrx2@nrx2:~$ 
```
Trong đó :
- Cột 1 thể hiện loại tệp và quyền (permission)
- Cột 2 thể hiện bộ nhớ
- Cột 3 thể hiện quyền sở hữu
- Cột 4 thể hiện nhóm sở hữu
- Cột 5 thể hiện kích thước tệp tính theo byte
- Cột 6 thể hiện thời gian tạo hoặc cập nhật lần cuối
- Cột cuối là tên của file hoặc thư mục

# Quyền truy cập file và thư mục
3 Nhóm quyền
#|Description
-|-
Owner | Chủ sở hữu, xác định những hành động của chủ sở hữ có thể thực hiện với tệp
Group | Nhóm, xác định những hành động các thành viên trong nhóm có thể thực hiện với tệp 
Other | Xác định các hành động mà người khác có thể thực hiện đối với file


Eg: 
```
drwxr-xr-x.  6 root root     4096 Nov 11 22:08 sysconfig
-rw-r--r--.  1 root root      449 Apr 11  2018 sysctl.conf
drwxr-xr-x.  2 root root       28 Nov 11 22:01 sysctl.d
drwxr-xr-x.  4 root root      151 Nov 11 22:01 systemd
```
---
- `r` quyền đọc
- `w` quyền ghi hay sửa đổi tệp
- `x` quyền thực thi
- `-` không có quyền
---
- Ký tự 1 cho biết đó là file hay thư mục
- Ký tự thứ 2-4 thể hiện quyền của chủ sở hữu
- Ký tự thư 5-7 thể hiện quyền của nhóm
- Ký tự thứ 8-10 thể hiện quyền của các người dùng khác

# Thay đổi quyền

Để thay đổi quyền ta sử dụng lệnh `1`chmod`, `chmod` ta có thể sử dụng ở 2 chế độ

__Chế độ tượng trưng__

- `+` Thêm quyền được chỉ định cho file hoặc thư mục
- `-` Loại bỏ quyền được chỉ định cho file hoặc thư mục
- `=` Gán quyền được chỉ định cho file hoặc thư mục

Để thêm quyền thực thi cho chủ sở hữu vơi file file.txt: # chmod u+x file.txt

Để loại bỏ quyền ghi của các người dùng khác: # chmod o-w file.txt

Để gán cho các người dùng thuộc group quyền đọc và ghi mà không có thực thi: # chmod g=rw file.txt

# Chế độ tuyệt đối
Ngoài ra ta có thể thay đổi quyền của file và thư mục ở chế độ tuyệt đối, ở chế độ này mỗi quyền được gán một giá trị số, bảng sau đây mô ta các quyền tương ứng với cá giá trị

Number	| Permissions |	Descriptions
-|-|-
0	| ---	|Không có quyền gì
1	| --x	|Quyền thực thi
2	| -w-	|Quyền ghi
3	|-wx	2(w) + 1(x) = 3: |Quyền ghi và thực thi 
4	|r---	|Quyền đọc
5	|r-x	4(r) + 1(x) = 5: |Quyền đọc và thực thi
6	|rw-	4(r) + 2(w) = 6: |Quyền đọc và ghi
7	|rwx	4(r) + 2(w) + 1(x) = 6: |Full quyền

Ví dụ với file `file.txt`

Để chủ sở hữu có full quyền, group có quyền đọc và ghi còn các người dùng khác không có quyền: `chmod 760 file.txt`
# Thay đổi chủ sở hữu
Để thay đổi người sở hữu ta sử dụng lệnh `chown`, đối với người dùng `root` có thể thay đổi tất cả quyền sở hữu của file và thư mục, ngoài ra đối với các người dùng khác chỉ có thể thay đổi quyên sở hữu của file hoặc thư mục mà họ sở hữu.

Cú pháp:`chown <user> <file or directory>`

Ta có thể thay <user> bằng id của người dùng thay vì tên người dùng.

Ví dụ: `# chown www-data file.txt ` Sẽ thay đổi chủ sở hữu của `file.txt `thành `www-data (Người dùng apache)`

# Thay đổi nhóm sở hữu

Để thay đổi nhóm sở hữu ta sử dụng lệnh `chgrp`

Cú pháp: `chgrp <group> <file or directory>`

Ví dụ:

`chgrp apache file.txt`Để thay đổi nhóm sở hữu của `file.txt` thành nhóm apache.