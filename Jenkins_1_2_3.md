**Lesson 1: Introduction & getting started**
  - Jenkins is java application
  - Used for continuous intergration and continuous delivery
  
  Để cài đặt được Jenkins thì yêu cầu cần cài đặt Java và Docker trên Windows
  Sau đó download Jenkins từ link: https://www.jenkins.io/download/ (trên Windows có thể tải bản .war hoặc tải bản .msi để cài đặt)
  
  Sau khi cài đặt Jenkins xong, có thể truy cập đường dẫn sau trên browser để khởi chạy Jenkins: localhost:8088 (port 8088 hay bao nhiêu là tùy bạn setting khi cài đặt bằng .msi)
  
  Riêng với bản .war thì bạn truy cập đến folder chứa file jenkins.war và có thể sử dụng câu lệnh sau để khởi chạy Jenkins: java -jar jenkins.war --httpPort:8089
  
  ![image](https://user-images.githubusercontent.com/19218660/208485400-1077a01a-f2ac-42c1-8836-e2a8732c3460.png)
  
  Sử dụng mật khẩu trong terminal để đăng nhập vào và cài đặt plugin trên Jenkins
  
  ![image](https://user-images.githubusercontent.com/19218660/208486047-1e1f0b7c-3d8b-44cf-9e37-0b8974464a27.png)

  Sau khi chạy cài đặt plugin thành công, sẽ hiển thị dashboard của Jenkins
  
  ![image](https://user-images.githubusercontent.com/19218660/208486445-5468fdb0-eb62-4ce5-aae0-48879578a2c3.png)

**Lesson 2: Run Jenkins on Tomcat**

  Download Tomcat từ link: https://tomcat.apache.org/download-10.cgi
  
  Setup JAVA_HOME, CLASSPATH and PATH, vi du: set JAVA_HOME=C:\Program Files\Java\jdk-17.0.5
  
  Khoi dong Tomcat bang cau lenh: .\bin\startup.bat
  
  Truy cap localhost:8080 de kiem tra
  
  ![image](https://user-images.githubusercontent.com/19218660/208732898-af5d6b0c-e43b-48e9-b575-3ee912252947.png)

  
**Lesson 3: Run Jenkins in Docker**

  Download docker ztừ link: https://www.docker.com/docker-windows
  
  Cài đặt và run docker, kiểm tra docker bằng câu lệnh sau:
  
  `docker ps`
  
  `docker info`
  
  Pull and run the cloudbees JENKINS container bằng câu lệnh sau:
  
  `docker pull jenkins/jenkins`
  
  `docker run -p 8080 --name=jenkins-master jenkins/jenkins`
  
  Khi khởi chạy Jenkins thì sẽ tạo ra 1 password, nếu bạn bị quên mất thì có thể chạy câu lệnh sau để xem lại:
  
  `docker exec jenkins-master cat /var/jenkins_home/secrets/initialAdminPassword`
  
  **Publish Jenkins with Ngrok**
  
  Cài đặt ngrok từ link: https://dashboard.ngrok.com/get-started/setup
  
  Ở phiên bản miễn phí, chúng ta sẽ bị giới hạn ở các điểm:

      - Chỉ hỗ trợ HTTP và TCP
      - Subdomain ngẫu nhiên
      - Chỉ chạy được 1 proccess ngrok tại 1 thời điểm
      - Giới hạn 4 tunnel / 1 process
      - Giới hạn 40 connections / 1 phút
      
  Chạy ngrok.exe, giao diện của ngrok tương tự cmd
  
  Tạo tài khoản ngrok và set authtoken bằng câu lệnh sau:
  
  `ngrok config add-authtoken [mã token của tài khoản]`
  
  Publish port 8080 với cú pháp sau:
  
  `ngrok http 8080`
  
  Từ giờ bạn có thể truy cập Jenkins từ máy khác với link của ngrok.
