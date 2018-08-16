
 <a name="content">Nội dung</a>

- Nội dung của bài viết nói về cách tạo nên Docker Compose file để sử dụng khi có nhu cầu tạo ra nhiều Docker Container Applications.

- Nội dung sẽ chỉ nói về cú pháp của Docker Compose file với phiên bản 3 (version 3). Nội dung dưới đây sẽ mô tả qua về cấu trúc của Compose file.

+ Một Compose file được sử dụng theo cú pháp của [YAML](http://yaml.org/) để định nghĩa ra các services, networks và volumes. Mặc định đường dẫn để quy định sử dụng cho Compose file là `./docker-compose.yml`.

Một Compose file có thể có phần mở rộng của file là `.yml` hoặc `.yaml`

+ Một dịch vụ được định nghĩa bao gồm cấu hình được áp dụng cho mỗi container chạy dịch vụ đó, giống như việc sử dụng thông qua các tham số của dòng lệnh `docker container create`. Tương tự, network và volume cũng được sử dụng để quy định tương tự với `docker netwok create` và `docker volume network`.

+ Với `docker container create`, các tùy chọn có thể khai báo trong Dockerfile có thể có là `CMD, `EXPOSE`, `VOLUME` hay `ENV` và được xem như là những mặc định. Tuy nhiên, ta không cần phải khai báo lại chúng trong `docker-compose.yml`

+ Cấu trúc của `compose-file.yml` tuân thủ theo định dạng sau:

        <key>: <option>: <value>
