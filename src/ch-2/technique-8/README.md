# technique 8: Linking containers for port isolation

- run mysql container với name là `wp-mysql`
  ```shell
  sudo docker run --name wp-mysql -e MYSQL_ROOT_PASSWORD=yoursecretpassword -d mysql
  ```

- run wordpress container và connect tới container có tên `wp-mysql`
  ```shell
  sudo docker run --name wordpress --link wp-mysql:mysql -p 10003:80 -d wordpress
  ```

- chứng minh đã kết nối thành công
  - tạo `wp` database trong wp-mysql container
    ```shell
    sudo docker exec -it wp-mysql bash
    mysql -u root -p
    create database wp;
    ```
  - truy cập vào [link](http://localhost:10003) và thực hiện setup cho database
    - tên database: wp
    - tên người dùng: root
    - mật khẩu: yoursecretpassword
    - database host: wp-mysql
  - kiểm tra xem `wp` db đã tạo ra các bảng chuyên dụng chưa
    ```shell
    use wp;
    show tables;
    ```
