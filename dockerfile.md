
# 1. Dockerfile Commands
## 1.1 FROM
- Dùng để chỉ ra image được build từ đâu (từ image gốc nào)
```sh
FROM kalilinux

hoặc có thể chỉ rõ tag của image gốc

FROM kalilinux/kali-linux-docker:latest
```

## 1.2 RUN
- Dùng để chạy một lệnh nào đó khi build image, ví dụ về một `Dockerfile`
```sh
FROM FROM kalilinux
RUN apt-get clean
RUN apt-get update -y
```


## 1.3 CMD
- Lệnh CMD dùng để truyền một lệnh của Linux mỗi khi thực hiện khởi tạo một container từ image (image này được build từ `Dockerfile`)

```sh 
CMD ["/bin/bash"]
```
