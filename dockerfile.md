
# 1. Dockerfile Commands
## 1.1 FROM
- Dùng để chỉ ra image được build từ đâu (từ image gốc nào)
```sh
FROM kalilinux

hoặc có thể chỉ rõ tag của image gốc

FROM kalilinux/kali-linux-docker:latest
```

## 1.2 MAINTAINER
- Command này là tùy chọn, có thể có hoặc không. Nó chưa thông tin của người tiến hành xây dựng lên images.
```sh

MAINTAINER huutuan-kma<huutuanbg97@gmail.com>

```

## 1.3 RUN
- Dùng để chạy một lệnh nào đó khi build image, ví dụ về một `Dockerfile`
```sh
FROM FROM kalilinux
RUN apt-get clean
RUN apt-get update -y
```


## 1.4 CMD
- Lệnh CMD dùng để truyền một lệnh của Linux mỗi khi thực hiện khởi tạo một container từ image (image này được build từ `Dockerfile`)

```sh 
CMD ["/bin/bash"]
```
- Mỗi Dockerfile chỉ có một câu lệnh CMD, nếu như có nhiều hơn một câu lệnh CMD thì chỉ có câu lệnh CMD cuối cùng được sử dụng.
## 1.5 Khác
- Các câu lệnh khác trong docker sẽ 



# 2. Dockerfile nội dung

```sh
FROM kalilinux/kali-linux-docker:latest

MAINTAINER huutuan-kma<huutuanbg97@gmail.com>

ENV DEBIAN_FRONTEND noninteractive
ENV TERM xterm-256color

RUN rm -fR /var/lib/apt/
RUN apt-get clean
RUN apt-get update -y
RUN apt-get install -y software-properties-common && apt-get update -y
RUN apt-get install -y kali-linux-full --fix-missing
RUN apt-get install -y git colordiff colortail unzip vim tmux xterm zsh curl telnet strace ltrace tmate
RUN updatedb

CMD ["/bin/bash"]
```
