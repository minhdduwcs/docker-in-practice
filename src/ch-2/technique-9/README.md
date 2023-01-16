# technique 9: Setting up a local Docker registry

- tạo một local registry server
  ```shell
  sudo docker run -d -p 5000:5000 --restart=always --name registry registry:2
  ```

- thực hiện test local registry: copy image từ docker hub sang local registry
  - pull ubuntu:16.04 image từ docker hub
    ```shell
    sudo docker pull ubuntu:16.04
    ```
  - gán thêm tag cho ubuntu:16.04 image
    ```shell
    sudo docker tag ubuntu:16.04 localhost:5000/ubuntu
    ```
  - push image lên local registry
    ```shell
    sudo docker push localhost:5000/ubuntu
    ```
  - xóa các ubuntu:16.04 locally-cached image
    ```shell
    sudo docker image rm ubuntu:16.04
    sudo docker image rm localhost:5000/ubuntu
    ```
  - pull ubuntu image từ local registry
    ```shell
    sudo docker pull localhost:5000/ubuntu
    ```
