# technique 1: Open your Docker daemon to the world

- shut down docker daemon
  ```shell
  sudo service docker stop
  ```

- kiểm tra xem docker daemon đã tắt hay chưa
  ```shell
  ps -ef | grep -E 'docker(d| -d| daemon)\b' | grep -v grep
  ```

- restart docker daemon và define host server để cho phép người khác truy cập
  ```shell
  sudo dockerd -H tcp://0.0.0.0:2375
  ```

- 2 cách để connect từ bên ngoài
  - sử dụng `-H` option
    ```shell
    docker -H tcp://192.168.1.11:2375 ps -a
    ```
  - sử dụng environment variable
    ```shell
    export DOCKER_HOST=tcp://192.168.1.11:2375
    docker ps -a
    ```
