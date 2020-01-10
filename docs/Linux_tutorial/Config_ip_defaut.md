# Cấu hình IP tĩnh
---

1. Sau khi login hệ thống chúng ta vào thư mục sau: /etc/sysconfig/network-scripts/  bằng lệnh:
```
cd  /etc/sysconfig/network-scripts/
```
2. Mở file tên card mạng bằng quyền sudo để có quyền sửa file.

```
sudo vi ifcfg-ens33
```

Nhấn phím `Insert` trên bàn phím và Sửa thông số bôi đậm như hình:

TYPE=”Ethernet”

PROXY_METHOD=”none”

BROWSER_ONLY=”no”

___BOOTPROTO=”static”___

DEFROUTE=”yes”

IPV4_FAILURE_FATAL=”no”

IPV6INIT=”yes”

IPV6_AUTOCONF=”yes”

IPV6_DEFROUTE=”yes”

IPV6_FAILURE_FATAL=”no”

IPV6_ADDR_GEN_MODE=”

stable-privacy”

NAME=”ens33″

UUID=”1eff6d2b-3fd6-405b-9e78-cafb7fbc2e34″

DEVICE=”ens33″

ONBOOT=”yes”

___IPADDR=192.168.1.111___

___GATEWAY=192.168.1.1___

___NETMASK=255.255.255.0___

___DNS1=8.8.8.8___

___DNS2=8.8.4.4___

Sau đó `:wq` để thoát và lưu

3. Khởi động lại card mạng bằng lệnh :
```
systemctl restart network.service
```

Kiểm tra `ip` đã được cấu hình sử dụng lệnh :
```
ip addr
```