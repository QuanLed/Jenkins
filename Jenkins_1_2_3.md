Lesson 1: Introduction & getting started
  - Jenkins is java application
  - Used for continuous intergration and continuous delivery
  
  Để cài đặt được Jenkins thì yêu cầu cần cài đặt Java và Docker trên Windows
  Sau đó download Jenkins từ link: https://www.jenkins.io/download/ (trên Windows có thể tải bản .war hoặc tải bản .msi để cài đặt)
  
  Sau khi cài đặt Jenkins xong, có thể truy cập đường dẫn sau trên browser để khởi chạy Jenkins: localhost:8088 (port 8088 hay bao nhiêu là tùy bạn setting khi cài đặt bằng .msi)
  Riêng với bản .war thì bạn truy cập đến folder chứa file jenkins.war và có thể sử dụng câu lệnh sau để khởi chạy Jenkins: java -jar jenkins.war --httpPort:8089
  