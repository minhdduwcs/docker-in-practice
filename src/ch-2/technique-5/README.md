# technique 5: Using Docker in your browser

- stop và restart docker daemon ở port 2375
  ```shell
  sudo service docker stop
  sudo dockerd -H tcp://0.0.0.0:2375 --api-cors-header=*
  ```

- pull code từ github
  ```shell
  git clone https://github.com/aidanhs/Docker-Terminal.git
  cd Docker-Terminal
  ```

- chạy server
  ```shell
  python2 -m SimpleHTTPServer 8000
  ```
