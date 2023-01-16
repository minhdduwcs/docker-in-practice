# technique 10: Finding and running a Docker image

- search các image match với `node` keyword trên docker hub
  ```shell
  sudo docker search node
  ```

- pull `node` image từ docker hub
  ```
  sudo docker pull node
  ```

- tạo một container từ `node` image
  ```shell
  sudo docker run -t -i node /bin/bash
  ```
