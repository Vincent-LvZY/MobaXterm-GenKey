# MobaXterm-GenKey
你懂的！！


## 本地启动
需要安装Python3!!!
```
pip install --no-cache-dir -r requirements.txt
python app.py
```

## Docker
```
docker pull malaohu/mobaxterm-genkey
docker run -d -p 5000:5000 malaohu/mobaxterm-genkey
```
## SSH 命令生成镜像
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

![image](https://img14.360buyimg.com/ddimg/jfs/t1/327451/37/1655/17390/68940230F93909c3f/80f2e5a285489ac1.jpg)

### 激活方式
直接放到软件目录即可！



核心内容来自：https://github.com/flygon2018/MobaXterm-keygen
详细介绍文章：https://51.ruyo.net/17008.html
