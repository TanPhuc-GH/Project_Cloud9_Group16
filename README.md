# NHÓM 16
Thành viên:
Nguyễn Duy Thanh - 20110565\n
Nguyễn Tuấn Trung - 20110\n
Trương Tấn Phúc - 20110544\n
# ĐỀ TÀI : TÌM HIỂU VÀ XÂY DỰNG ỨNG DỤNG MINH HỌA DỊCH VỤ AWS CLOUD9

# AWS CLOUD9 LÀ GÌ ?
AWS Cloud9 là môi trường phát triển tích hợp (IDE) dựa trên đám mây cho phép bạn viết, chạy và gỡ lỗi mã chỉ bằng một trình duyệt. Môi trường này bao gồm một trình soạn mã, trình gỡ lỗi và thiết bị đầu cuối. Cloud9 được trang bị sẵn các công cụ thiết yếu cho các ngôn ngữ lập trình phổ biến, bao gồm JavaScript, Python, PHP và nhiều ngôn ngữ khác, nhờ vậy bạn không cần cài đặt tệp hoặc cấu hình máy phát triển để bắt đầu các dự án mới. Vì IDE Cloud9 là nền tảng dựa trên đám mây, nên bạn có thể làm việc với các dự án từ văn phòng, nhà hoặc bất cứ nơi đâu thông qua máy được kết nối với internet\n
# LỢI ÍCH CỦA DỊCH VỤ CLOUD 9
  - Viết mã chỉ bằng một trình duyệt \n
  - Viết mã cùng nhau trong thời gian thực \n
  - Xây dựng các ứng dụng Serverless một cách dễ dàng \n
  - Chuyển truy cập thiết bị đầu cuối đến AWS \n
  - Bắt đầu dự án mới nhanh chóng \n
# CÁC DỊCH VỤ KHÁC ĐƯỢC SỬ DỤNG TRONG ỨNG DỤNG
- Amazon EC2: dịch vụ cung cấp các máy tính ảo để người dùng chạy các ứng dụng máy tính của riêng họ \n
- Amazon RDS: dịch vụ giúp người dùng dễ dàng thiết lập, vận hành và thay đổi quy mô cơ sở dữ liệu trên đám mây

# XÂY DỰNG ỨNG DỤNG MINH HỌA
- Đăng ký các dịch vụ
- Đăng nhập vào AWS 
-	Đăng ký dịch vụ RDS 
	![image](https://user-images.githubusercontent.com/94969319/206835665-9ccd82c3-fe15-41ef-988f-ee5210d27714.png)

Cấu hình options cho RDS 
 ![image](https://user-images.githubusercontent.com/94969319/206835669-618c1d8c-5586-4479-9be6-76c9eb43dfe4.png)
![image](https://user-images.githubusercontent.com/94969319/206835673-85d43d9f-4dc7-48df-b53b-a75a9f9e7288.png)

Sau khi tạo thành công, DB sẽ hiển thị trong bảng databases 
![image](https://user-images.githubusercontent.com/94969319/206835677-3d0fefa1-9b10-4d2c-b0d5-984521bfed6e.png)

Cấu hình dịch vụ EC2 
![image](https://user-images.githubusercontent.com/94969319/206835678-9e76d4d3-b22b-4cf8-965b-a89eebef4d1b.png)

Lựa chọn security group tương ứng với RDS vừa tạo 
![image](https://user-images.githubusercontent.com/94969319/206835679-2c8a5325-5997-44f5-883c-17d5f91a91b5.png)

Edit Inbound rules
 ![image](https://user-images.githubusercontent.com/94969319/206835680-785bcbf1-b88a-445f-91a5-f407ea009e39.png)

Tạo môi trường Cloud9
 ![image](https://user-images.githubusercontent.com/94969319/206835681-cb3f546d-5745-476a-b286-b28379f174e4.png)

Thiết lập cài đặt cho môi trường 
 ![image](https://user-images.githubusercontent.com/94969319/206835684-918e43f3-6bf8-4374-a4d5-94237a045f75.png)

Sau khi tạo thành công, môi trường sẽ được hiển thị tại đây 
![image](https://user-images.githubusercontent.com/94969319/206835687-8d689d45-eed0-4553-9003-a21a17181758.png)

Nhấp chọn môi trường vừa tạo 
![image](https://user-images.githubusercontent.com/94969319/206835692-04d46659-de22-4454-b91b-552749e6a5e1.png)

Nhấn nút “Open in Cloud9” để mở IDE 
![image](https://user-images.githubusercontent.com/94969319/206835693-6c25ef85-7d56-4d3c-84c4-046e92650059.png)

# Cài đặt ứng dụng minh họa chạy trên nền tảng IDE của Cloud9
B1: git clone code từ repository theo link github sau: 
	https://github.com/TanPhuc-GH/Project_Cloud9_Group16.git
B2: Cài đặt apache-tomcat theo hướng dẫn của video sau
	(1) How To Install And Configure Apache Tomcat Server In Ubuntu Linux - YouTube
B3: Tại thư mục lib\out\artifacts ta copy 2 folder Web_Project_MVC_war và Web_Project_MVC_war_exploded và bỏ vào folder apache-tomcat-9.0.70/webapps
![image](https://user-images.githubusercontent.com/94969319/206835710-72ef4356-f911-495e-9664-38d55c14f447.png)
![image](https://user-images.githubusercontent.com/94969319/206835713-baff1e2f-0926-4123-997a-50cbdc5d6ec0.png)
B4: Vào file pom.xml của project, thêm dependency sau
![image](https://user-images.githubusercontent.com/94969319/206835718-15d2a07f-ece7-4256-a83c-213d0bc929b9.png)
B5: cd đến thư mục project, chạy lệnh “mvn clean install” để build project
![image](https://user-images.githubusercontent.com/94969319/206835719-afb0c3b6-84cd-410b-9c6c-1b11d497ed3d.png)
B6: cd đến thư mục apache-tomcat-9.0.70/bin, chạy lệnh “sh startup.sh” để khởi động server tomcat
![image](https://user-images.githubusercontent.com/94969319/206835723-af18be4f-48bf-4956-9f79-2abb9715f8a6.png)
B7: nhấn preview running application  
![image](https://user-images.githubusercontent.com/94969319/206835729-283c8e2e-65ef-48b2-a126-a7bc3eef59a5.png)
Một cửa sổ hiện ra, coppy đường link và dán vào trình duyệt
![image](https://user-images.githubusercontent.com/94969319/206835734-925ac941-3a65-46f6-b0ec-75d305636b3c.png)
B8: Nhấn vào manager App, sau đó nhấn vào đường link /Web_Project_MVC_war_exploded để mở trang web

# KẾT LUẬN 
1. Kết quả đạt được
Sau quá trình tìm hiểu và thực hiện đề tài, 
-	Nắm vững kiến thức về dịch vụ Cloud9, cũng như các dịch vụ sử dụng kết hợp như RDS, EC2…
-	Xây dựng thành công database bằng dịch vụ RDS và thực hiện kết nối đến ứng dụng
2. Các hạn chế :
-	Do tài khoản free nên còn hạn chế nhiều tính năng khi sử dụng các dịch vụ
-	Một số dịch vụ hỗ trợ chưa tốt cho ứng dụng minh họa trong việc triển khai, chạy ứng dụng
3. Hướng phát triển trong tương lai
-	Mở rộng thêm các chức năng còn thiếu trong ứng dụng
-	Tích hợp thêm nhiều dịch vụ khác hỗ trợ cho việc triển khai ứng dụng
-	Khám phá thêm các chức năng khác của dịch vụ Cloud



