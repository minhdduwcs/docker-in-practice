# Docker In Practice

## chapter 2: Understanding Docker

- **2.1 Docker’s architecture**
  - giới thiệu sơ qua về docker: docker daemon, docker client, private docker registry, docker hub và các public docker registry khác

- **2.2 The Docker daemon**
  - [technique-1](src/ch-2/technique-1): cho phép người khác có thể truy cập vào docker server
  - [technique-2](src/ch-2/technique-2): chạy container như một daemon và sử dụng `--restart` flag
  - [technique-3](src/ch-2/technique-3): thay đổi folder lưu trữ data của docker

- **2.3 The Docker client**
  - [technique-4](src/ch-2/technique-4): theo dõi các API call giữa docker client và docker daemon
  - [technique-5](src/ch-2/technique-5): sử dụng Docker Terminal để truy cập docker từ web
  - [technique-6](src/ch-2/technique-6): sử dụng `-p` flag để map container port với host port
  - [technique-7](src/ch-2/technique-7): tạo ra một user-defined network để giúp các container giao tiếp với nhau
  - [technique-8](src/ch-2/technique-8): thực hiện giao tiếp giữa các container mà không sử dụng user-defined network

- **2.4 Docker registries**
  - [technique-9](src/ch-2/technique-9): tạo một local registry

- **2.5 The Docker Hub**
  - [technique-10](src/ch-2/technique-10): tìm docker image bằng terminal
