# GIT REPOSTORY

# Trạng thái của REPOSTORY
![image](https://git-scm.com/book/en/v2/images/lifecycle.png)

Có 4 trạng thái

- `Untracked` : Trạng thái chưa được git theo dõi, vẫn là file thông thường.
- `Staged` : Trạng thái đã được git theo dõi, có thể commit
- `Unmodified`: File khi chưa có gì chỉnh sửa.
- `Modified`: Đã có chỉnh sửa.

Khi tạo file hoặc clone từ github về thì file đó sẽ bắt đầu với trạng thái  `Untracked` sử dụng lệnh `git add` thì nó sẽ ở  `Staged` khi đó ta có thể commit file và push lên github.

# Tạo local repository
Bước 1: Cài đặt git 

Bước 2: Cấu hình username và email

Bước 3: Tạo local repository

`Thao tác tạo remote repo:`
```
# Cấu hình username và email cho repo
$ git config --global user.name 'what is the name'
$ git config --global user.email "what is the gmail"
 
# Tạo local repo
# git init
```
# Liên kết local repot với github

- Thêm remote repo :

```
$ git remote add mybaby https://github.com/norealy/basicLearntoGitHub
```


- Xem thông tin remote server đã thêm :
```
$ git remote -v
```
lấy dữ liệu từ cái `mybaby` kia về thì chỉ cần sử dụng lệnh `$git fetch mybaby`

# Sự khác nhau giữa `clone`, `fetch` và `pull`
Cả ba loại đều là lấy dữ liệu:

`git clone` : Sao chép toàn bộ dữ liệu trên repository và cả thiết lập nữa. Thường sử dụng khi lấy dữ liệu từ 1 Git mới về.

`git pull` lấy toàn bộ dữ liệu remote repostorty gộp vào cái branch đang làm việc( ĐỒng bộ từ git về).

`git fetch` Lấy toàn bộ dữ liệu từ remote repostory nhưng cho phép gộp thủ công vào branch nào đó trên thư mục GIt ở máy tính.
