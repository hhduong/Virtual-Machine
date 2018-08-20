# Cách cài máy ảo bằng VMware Workstation 12
***
## Mục lục
[1. Tổng quan về VMWare Workstation](#tong-quan)

[2. Cách tạo máy ảo trên VMWare Workstation](#huong-dan)

## <a name = "tong-quan"></a> 1. Tổng quan về VMWare Workstation
 
- VMware Workstation là một phần mềm ảo hóa desktop mạnh mẽ dành cho các nhà phát triển/kiểm tra phần mềm và các chuyên gia IT cần chạy nhiều HĐH một lúc trên một máy PC.
  
* VMware workstation có nhiều phiên bản cho nhiều hệ điếu hành khác nhau như Windows, Linux, Mac OS… VMware workstation là phần mềm có tính phí.
* Người dùng có thể chạy các HĐH Windows, Linux, Netware hay Solaris x86 trên các máy ảo di động mà không cần phải khởi động lại hay phân vùng ổ cứng.
* Máy ảo sử dụng các nguồn tài nguyên phần cứng của máy vật lý mà nó chạy trên đó , những máy vật lý này được gọi là hệ thống máy chủ ảo hóa . Máy ảo có thiết bị ảo cung cấp các chức năng tương tự như vật lý phần cứng , nhưng  với những lợi ích bổ sung của nó là tính di động, dể quản lý và bảo mật.
* Ngoài việc tạo máy ảo mới, mở một máy tính có sẵn, VMware workstation còn cung câp cho bạn rất nhiều tính năng hữu ích khác, thao tác dể dàng và vượt trội hơn những phần mềm tương tự.
    * Tính năng quản lý các mạng máy tính ảo với Virtual Network Editor
    * Tính năng chia sẽ máy ảo đóng vai trò như là một VMware server
    * Tính năng kết nối từ xa đến VMware server
    * Tính năng Map ổ đĩa cứng ảo vào máy tính thật, giúp bạn có thể dể dàng lấy dữ liệu mà không cần phải bật máy tính ảo lên
  
- Giao diện của VMware workstation 12

![Imgur](https://i.imgur.com/tm2eSp6.png")

## <a name = "huong-dan"></a> 2. Cách tạo máy ảo trên VMware Workstation

- Bước 1: Trên màn hình chính, chọn `Create a new Virtual Machine` để tạo máy ảo mới

![Imgur](https://i.imgur.com/fVWY567.png")
Tại đây ta thấy có 2 lựa chọn là `Typical` và `Custom`. `Typical` là cài đặt theo những tùy chọn mặc định, `Custom` là tùy chỉnh theo ý người dùng.
Ở đây tôi chọn `Custom`.

- Bước 2: Lựa chọn ổ đĩa.

![Imgur](https://i.imgur.com/oTAGZHz.png")

- Ở đây có 3 lựa chọn:
  
  - Cài đặt từ ổ đĩa
  - Cài đặt từ file .iso
  - Cài đặt sau (Phần cứng trống)

 Tôi lựa chọn cài sau.

- Bước 3: Lựa chọn hệ điều hành và phiên bản.
![Imgur](https://i.imgur.com/2wnOCIM.png")
Ở đây tôi chọn Linux với hệ điều hành Ubuntu 64 bit.
- Bước 4: Đặt tên và lựa chọn vị trí lưu máy ảo trên máy tính.
![Imgur](https://i.imgur.com/NS8jLlF.png")
- Bước 5: Lựa chọn số nhân và số lõi cpu cho máy ảo
![Imgur](https://i.imgur.com/NaZM3de.png")
 Ở đây tôi chọn mặc định.
- Bước 6: Lựa chọn dung lượng RAM cho máy ảo
![Imgur](https://i.imgur.com/2ArFBJu.png")
 Tùy vào dung lượng RAM của máy chủ mà chúng ta lựa chọn cho phù hợp. Ở đây tôi chọn mức 2GB
- Bước 7: Lựa chọn card mạng cho máy ảo
![Imgur](https://i.imgur.com/dmA8PCj.png")

 Ở đây sẽ có 4 tùy chọn:

- Card Bridge: Card này sẽ sử dụng chính card mạng thật của máy để kết nối ra ngoài internet(card ethernet hoặc wireless). 
Do đó khi sử dụng card mạng này IP của máy ảo sẽ cùng với dải IP của máy thật.Lưu ý: Card Bridge trên máy ảo chỉ có thể giao tiếp với card mạng thật trên máy thật.
- Card NAT: Card này sẽ Nat địa chỉ IP của máy thật ra một địa chỉ khác cho máy ảo sử dụng.
  - Card NAT chỉ có thể giao tiếp với card mạng ảo VMnet8 trên máy thật.
  - Card NAT chỉ có thể giao tiếp với các card NAT trên các máy ảo khác.
  - Card NAT không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối. 
  - Tuy nhiên nhờ cơ chế NAT được tích hợp trong VMWare, máy tính ảo có thể gián tiếp liên lạc với mạng vật lý bên ngoài.
- Card Host-only:
  - Card Host-only chỉ có thể giao tiếp với card mạng ảo VMnet1 trên máy thật.
  - Card Host-only chỉ có thể giao tiếp với các card Host-only trên các máy ảo khác.
  - Card Host-only không thể giao tiếp với mạng vật lý mà máy tính thật đang kết nối.
- Lựa chọn cuối cùng đó là không cấu hình kết nối mạng.

Ở đây tôi chọn NAT.

- Bước 8: Lựa chọn I/O Controller Types
![Imgur](https://i.imgur.com/rCzD0lC.png")
Ở đây có 3 tùy chọn là BusLogic (không khả dụng ở những phiên bản hệ điều hành 64bit), LSI Logic và LSI Logic SAS.
Mặc định VMWare sẽ lựa chọn LSI Logic do nó được support rộng rãi hơn ở các phiên bản hệ điều hành. Ở đây tôi để mặc định.
- Bước 9: Lựa chọn kiểu ổ đĩa cho máy ảo
![Imgur](https://i.imgur.com/6clkIkS.png")
 Ta có 3 tùy chọn là:
 - IDE
 - SCSI
 - SATA

 Ở đây tôi để mặc định là `SCSI` bởi nó có hiệu năng tốt hơn.
- Bước 10: Lựa chọn ổ đĩa cho máy ảo.
![Imgur](https://i.imgur.com/h0Bexu6.png")
Tại đây có 3 lựa chọn:
  - Create a new virtual disk: Tạo mới một ổ đĩa ảo.
  - Use an existing virtual disk: Dùng lại ổ đĩa ảo đã được tạo.
  - Use a physical disk: Cho phép máy ảo truy cập vào ổ đĩa thật.
 Tôi chọn tạo mới một đĩa ảo.
- Bước 11: Thiết lập dung lượng cho ổ cứng
![Imgur](https://i.imgur.com/soLPNsI.png")
 Ở đây ta lựa chọn dung lượng lưu trữ cho ổ cứng.
 VMware có tùy chọn `Allocate all disk space now` cho phép ta sử dụng tất cả các dung lượng trống. 

 Ngoài ra, bạn cũng có 2 tùy chọn đó là:
 - Lưu ổ cứng thành 1 file `Store a virtual disk as a single file`.
 - Lưu ổ cứng thành nhiều file `Split virtual disk into multiple file`. 

 Tại đây tôi chọn dung lượng là 20GB và phân chia ổ cứng thành nhiều file.
- Bước 12: Lựa chọn nơi lưu file ổ cứng
![Imgur](https://i.imgur.com/Efq2FlL.png")
- Bước 13: Hoàn thành việc tạo máy ảo
Chọn `Customize Hardware` để tùy chỉnh những lựa chọn về phần cứng.

 Chọn `New CD/DVD` -> `Use ISO physical drive` để chọn file.iso của hệ điều hành muốn cài cho máy ảo ->`close` 
![Imgur](https://i.imgur.com/vzRAEza.png")
Cuối cùng chọn `Finish` để hoàn thành việc cài máy ảo.









  







