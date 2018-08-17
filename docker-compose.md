# Cách viết Docker Compose file.
 <a name="content">Nội dung</a>


+ Một Compose file được sử dụng theo cú pháp của [YAML](http://yaml.org/) để định nghĩa ra các services, networks và volumes. Mặc định đường dẫn để quy định sử dụng cho Compose file là `./docker-compose.yml`.

Một Compose file có thể có phần mở rộng của file là `.yml` hoặc `.yaml`

+ Một dịch vụ được định nghĩa bao gồm cấu hình được áp dụng cho mỗi container chạy dịch vụ đó, giống như việc sử dụng thông qua các tham số của dòng lệnh `docker container create`. Tương tự, network và volume cũng được sử dụng để quy định tương tự với `docker netwok create` và `docker volume network`.

+ Với `docker container create`, các tùy chọn có thể khai báo trong Dockerfile có thể có là `CMD, `EXPOSE`, `VOLUME` hay `ENV` và được xem như là những mặc định. Tuy nhiên, ta không cần phải khai báo lại chúng trong `docker-compose.yml`

+ Cấu trúc của `compose-file.yml` tuân thủ theo định dạng sau:

        <key>: <option>: <value>
        
 
# Compose file
### <a name="1">build</a>

    - Khai báo cho tùy chọn này được áp dụng vào trong quá trình build (build time).
    - `build` có thể được khai báo cùng với string là một đường dẫn tới ngữ cảnh build.
     Kết quả là một image có tên là `kali` được đánh tag là `tag` sẽ được build ra từ đường dẫn `.`
  
### <a name="8">cap_add, cap_drop</a>

    - Sử dụng để thêm hoặc loại bỏ khả năng của container. Ta có thể xem danh sách các khả năng của container qua [`man 7 capabilities`](https://linux.die.net/man/7/capabilities)

    - Ví dụ khai báo có thể là:
 
    cap_add:
         - ALL

    cap_drop:
        - NET_ADMIN
        - SYS_ADMIN

    

           

### <a name="8"> stdin_open, tty</a>
- Để có thể debug thì bạn cần 2 dòng:

```sh
    stdin_open: true
    tty: true

```
    
 # NỘi dung docker compose file.
 
 ```sh
version: '3'
services:
  kali:
    build: .
    cap_add:
      - NET_ADMIN
    stdin_open: true
    tty: true
    

```
 
 
