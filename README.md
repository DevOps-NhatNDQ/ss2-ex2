1. Các dòng lệnh linux đã chạy:

- Tạo user mới tên devops: adduser devops
- cấp quyền quản trị cho user vừa tạo: usermod -aG sudo devops
- sao chép Public Key từ tài khoản root sang thư mục cá nhân của devops: 
```
# Tạo thư mục lưu khóa SSH cho user devops
mkdir -p /home/devops/.ssh
 
# Sao chép file chứa các public key đã cấu hình của root sang cho devops
cp /root/.ssh/authorized_keys /home/devops/.ssh/
```
- Phân quyền cho thư mục .ssh và file authorized_keys của user devops:
```
chown -R devops:devops /home/devops/.ssh
chmod 700 /home/devops/.ssh
chmod 600 /home/devops/.ssh/authorized_keys
```

2. log Terminal kiểm tra lệnh sudo whoami
```
devops@0310263186:~$ sudo whoami
[sudo] password for devops:
root
devops@0310263186:~$
```