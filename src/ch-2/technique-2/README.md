# technique 2: Running containers as daemons

## 1. chạy container như một daemon

- chạy container như một daemon: sử dụng `-d` flag
  ```shell
  $ sudo docker run -d -i -p 1234:1234 --name daemon ubuntu:14.04 nc -l 1234
  ```

- để confirm container đang chạy ngầm: sử dụng telnet
  ```shell
  $ telnet localhost 1234
  hello daemon
  ```
  - để tắt telnet: `ctrl + ]` và `q`

- xem log của container sẽ thấy các message được gửi từ telnet
  ```shell
  $ sudo docker logs daemon
  ```

## 2. sử dụng `--restart` flag

- `--restart=always`: thực hiện stop container và restart docker daemon thì container đó sẽ được restart trở lại
  ```shell
  $ sudo docker run -d --restart=always --name=daemon ubuntu echo done
  ```

- `--restart=unless-stopped`: thực hiện stop container và restart docker daemon thì container đó sẽ không restart lại
  ```shell
  $ sudo docker run -d --restart=unless-stopped --name=daemon ubuntu echo done
  ```

- `--restart=on-failure`: chỉ restart khi exit code của container khác 0
  ```shell
  $ sudo docker run -d --restart=on-failure:10 --name=daemon ubuntu /bin/false
  ```
