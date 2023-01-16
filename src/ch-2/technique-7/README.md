# technique 7: Allowing container communication

- tạo ra một user-defined network
  ```shell
  sudo docker network create my_network
  ```

- tạo ra 2 blog container
  ```shell
  sudo docker run -d -p 10001:80 --name blog1 tutum/wordpress
  sudo docker run -d -p 10002:80 --name blog2 tutum/wordpress
  ```

- kết nối blog1 container vào user-defined network
  ```shell
  sudo docker network connect my_network blog1
  ```

- tạo ra ubuntu container và kết nối nó vào user-defined network
  ```shell
   sudo docker run -it --network my_network ubuntu:16.04 bash
  ```

- thực hiện giao tiếp giữa ubuntu container với blog1 và blog2 container
  - install curl package
    ```shell
    apt update && apt install -y curl
    ```
  - giao tiếp với blog1 container
    ```shell
    curl -sSL blog1 | head -n5
    ```
  - giao tiếp với blog2 container
    ```shell
    curl -sSL blog2 | head -n5
    ```
