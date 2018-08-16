# Nghiên cứu các lệnh cơ bản docker

## Pull một image từ Docker Hub
> docker pull {image_name}
## Liệt kê các images hiện có
> docker images
## Xóa một image
> docker rmi {image_id/name}
## Liệt kê các container đang chạy
> docker ps
---
> docker ps -a #Liệt kê các container đã tắt
## Xóa một container
> docker rm -f {container_id/name}
## Đổi tên một container
> docker rename {old_container_name} {new_container_name}
## Khởi động một container
> docker start {new_container_name}
---
> docker exec -it {new_container_name} /bin/bash
## Tạo mới một container, đồng thời khởi động với tùy chọn cổng và volume
> docker run --name {container_name} -p {host_port}:{container_port} -v {/host_path}:{/container_path} -it {image_name} /bin/bash
## Xem các thay đổi trên container
> docker diff {container_name}
## Commit các thay đổi trên container và image
> docker commit -m "message" {container_name} {image_name}
## Save image thành file .tar
> docker save {image_name} > {/host_path/new_image.tar}
## Tạo một image mới từ file .tar
> cat musashi.tar | docker import - {new_image_name}:latest
## Xem lịch sử các commit trên image
> docker history {image_name}
## Khôi phục lại images từ IMAGE_ID
> docker tag {image_id} {image_new_name}:{tag}a
## Build một image từ container
> docker build -t {container_name} .
Dấu . ở đây ám chỉ Dockerfile đang nằm trong thư mục hiện tại.
# Nghiên cứu các lệnh cơ bản docker compose
Commands:
```sh
  build              Build or rebuild services
  bundle             Generate a Docker bundle from the Compose file
  config             Validate and view the compose file
  create             Create services
  down               Stop and remove containers, networks, images, and volumes
  events             Receive real time events from containers
  exec               Execute a command in a running container
  help               Get help on a command
  kill               Kill containers
  logs               View output from containers
  pause              Pause services
  port               Print the public port for a port binding
  ps                 List containers
  pull               Pull service images
  push               Push service images
  restart            Restart services
  rm                 Remove stopped containers
  run                Run a one-off command
  scale              Set number of containers for a service
  start              Start services
  stop               Stop services
  top                Display the running processes
  unpause            Unpause services
  up                 Create and start containers
  version            Show the Docker-Compose version information
  ```
