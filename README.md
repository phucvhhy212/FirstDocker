# FirstDocker
** Cách sử dụng Docker để chạy 1 project: **
1. Kéo image về máy:
    
    Mở Command Prompt, nhập "docker pull phucvhhy212/my-localhost-image:v1.0.0".
    Nếu image đã được tải về thành công, màn hình sẽ trả về 1 dãy ngẫu nhiên ( là ID của image này )
    
2. Với image đã được tải về, ta tiên hành tạo 1 container sử dụng image này:
    
    Dùng câu lệnh: 
    docker run -dit --name my-localhost-container -p 8080:80 phucvhhy212/my-localhost-image:v1.0.0
    
    Trong đó: 
    
        docker run -dit: tạo 1 container, chạy bằng chế độ detached và tạo một terminal ảo để bạn có thể truy cập vào container đó.
      
        --name my-localhost-container: đặt tên cho container được tạo (tên tùy ý, ở đây là "my-localhost-container").
      
        -p 8080:80 ánh xạ cổng giao tiếp giữa client và server, ở đây là cổng 8080 máy tính chạy Docker và cổng 80 của container, khi ta gửi yêu cầu đến cổng 8080 trên           máy chủ sẽ được chuyển tiếp đến cổng 80 của container.
      
        phucvhhy212/my-localhost-image:v1.0.0 là tên image vừa được tải về
3. Sau khi container đã được chạy thành công, truy cập http://localhost:8080
