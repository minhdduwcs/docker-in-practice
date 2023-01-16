# technique 6: Using ports to connect to containers

- pull tutum-wordpress image từ Docker Hub
  ```shell
  sudo docker pull tutum/wordpress
  ```

- chạy blog container đầu tiên
  ```shell
  sudo docker run -d -p 10001:80 --name blog1 tutum/wordpress
  ```

- chạy blog container thứ 2
  ```shell
  sudo docker run -d -p 10002:80 --name blog2 tutum/wordpress
  ```

- có thể truy cập vào các blog container qua các port khác nhau
  - blog container 1: http://localhost:10001
  - blog container 2: http://localhost:10002
