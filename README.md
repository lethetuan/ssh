#Chi tiết cấu hình SSH trên Ubuntu Server

#bước 1 : update hệ thống

sudo apt update

sudo apt upgrade -y

#bước 2: Cài đặt và kích hoạt OpenSSH Server

sudo apt install openssh-server -y

#bước 3: Thiết lập tự động khởi động cùng hệ thống mỗi khi server khởi động lại

sudo systemctl enable --now ssh

#lệnh kiểm tra trạng thái ssh đã active (running) chưa

sudo systemctl status ssh


<img width="741" height="345" alt="image" src="https://github.com/user-attachments/assets/01b9616c-1d23-4f2a-a4ef-8424708f01e8" />

#Mở cổng trên Tường lửa (UFW) cho phép lưu lượng truy cập ssh qua cổng mặc định là cổng 22

sudo ufw allow ssh

sudo ufw enable

<img width="597" height="97" alt="image" src="https://github.com/user-attachments/assets/989e0911-bcc9-478f-a80c-56949a6a5694" />

#Tạo và sao chép SSH Key. Thực hiện trên Powershell của máy tính admin

# lệnh tạo ssh key ngay trên máy tính Window của Admin

ssh-keygen -t ed25519 -C "ten_may_tinh_cua_ban"

# sao chép public key ssh lên server linux

cd C:\Users\username\.ssh   (thay thế username bằng username máy tính của bạn)


type id_ed25519.pub | ssh tuan@10.1.1.30 "mkdir -p ~/.ssh && chmod 700 ~/.ssh && cat >> ~/.ssh/authorized_keys && chmod 600 ~/.ssh/authorized_keys"



<img width="801" height="621" alt="image" src="https://github.com/user-attachments/assets/9bf99a63-7ce6-4190-bf15-152fc3ec9001" />



<img width="1531" height="361" alt="image" src="https://github.com/user-attachments/assets/20b354c0-ce4c-4a06-8af3-a4de525d47bd" />


#đăng nhập ssh với lệnh 

ssh username@dia_chi_ip_server

<img width="699" height="483" alt="image" src="https://github.com/user-attachments/assets/3ba4fa4d-03ab-4c9a-a6ef-2f9bd40b09c2" />

Lưu trữ lại key đăng nhập

<img width="935" height="353" alt="image" src="https://github.com/user-attachments/assets/b2cd2fe5-9e1b-42c7-ad8e-c1cda56baaf0" />



