# MobaXterm-GenKey
你懂的！！

## Docker SSH 命令生成镜像
```
sudo git clone https://github.com/malaohu/MobaXterm-GenKey.git

cd MobaXterm-GenKey

sudo sed -i '1s/.*/FROM python:3.9-slim/; 2s/.*/LABEL maintainer="Vincent <123@163.com>"/' Dockerfile  ##邮箱地址自行修改

sudo docker build -t mobaxterm-keygen .
```
## 打包镜像
```
sudo docker save -o mobaxterm-keygen.tar mobaxterm-keygen:latest
sudo docker load -i mobaxterm-keygen.tar
```
## 启动命令
```
services:
  mobaxterm-keygen:
    image: mobaxterm-keygen:latest
    restart: always
    ports:
      - 5300:5000
```

## 使用方法
访问：IP:5300

![image](https://raw.githubusercontent.com/Vincent-LvZY/MobaXterm-GenKey/refs/heads/main/Screen.png)

### 激活方式
直接放到软件目录即可！



核心内容来自：https://github.com/flygon2018/MobaXterm-keygen
详细介绍文章：https://51.ruyo.net/17008.html
