# technique 4: Using socat to monitor Docker API traffic

- sử dụng socat để insert proxy Unix domain socker giữa docker client và docker daemon
  ```shell
  sudo socat -v \
    UNIX-LISTEN:/tmp/dockerapi.sock,fork \
    UNIX-CONNECT:/var/run/docker.sock &
  ```

- thực hiện một lệnh docker để xem các API call
  ```shell
  sudo docker -H unix:///tmp/dockerapi.sock ps -a
  ```
