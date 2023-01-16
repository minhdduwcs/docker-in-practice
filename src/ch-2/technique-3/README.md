# technique 3: Moving Docker to a different partition

- stop docker daemon
  ```shell
  sudo service docker stop
  ```

- restart docker daemon với `-g` flag
  ```shell
  sudo dockerd -g ~/Documents/docker-data
  ```

- kiểm tra các file data mà docker lưu trữ trong folder đó
  ```shell
  sudo su
  cd ~/Documents/docker-data
  ls
  ```
