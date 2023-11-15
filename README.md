# ntchat-api
wechat 机器人

### Docker中运行的微信机器人API

# 文档

# 运行

```bash
docker run -itd \
  --name=wechat \
  --net=host \
  iszmxw/wechat:1.0 \
  bash
```

### 整个下拉过程有点久
```bash
Unable to find image 'iszmxw/wechat:1.0' locally
1.0: Pulling from iszmxw/wechat
a55cd76a2ebe: Extracting [========================>                          ]  800.5MB/1.605GB
0e07225125bf: Download complete 
```

### 运行完成后如下

```bash
Unable to find image 'iszmxw/wechat:1.0' locally
1.0: Pulling from iszmxw/wechat
a55cd76a2ebe: Pull complete 
0e07225125bf: Pull complete 
Digest: sha256:b424fd719c9c2dda5cdc11ac038103293b3fe6c5ef02d65b205acb0559426f69
Status: Downloaded newer image for iszmxw/wechat:1.0
a4f8727964aa87ce731f49be581508c71533d39e67e7c3ea9fee354ba05a8fd1
```

### 进入容器

```bash
docker exec -it "容器ID" bash
# 查看 xrdp 状态
service xrdp status
# 运行 xrdp
service xrdp restart
# 运行 dbus
service dbus start  
```
### 这里是我运行的日志
```bash
root@VM-12-9-ubuntu:~# docker exec -it a4f8727964aa87ce731f49be581508c71533d39e67e7c3ea9fee354ba05a8fd1 bash
root@VM-12-9-ubuntu:/# service xrdp status
 * xrdp-sesman is not running
 * xrdp is not running
root@VM-12-9-ubuntu:/# service xrdp restart
 * Restarting Remote Desktop Protocol server                                                                                                                                     [ OK ] 
root@VM-12-9-ubuntu:/# service dbus start  
 * Removing stale PID file /var/run/dbus/pid.
 * Starting system message bus dbus                                                                                                                                                     dbus[92]: Unknown username "whoopsie" in message bus configuration file
                                                                                                                                                                                 [ OK ]
root@VM-12-9-ubuntu:/# 

```

### 容器的准备工作已经完成了，开始使用远程连接来控制服务器容器

- mac 可以下载一个 `Microsoft Remote Desktop`
<img width="167" alt="image" src="https://github.com/iszmxw/ocr/assets/31272102/16f2ff7f-d5cf-40b5-b06f-1c071402b8b8">

- windows 用户可以使用自带的远程

```
# Win+R 输入
mstsc
# Enter 回车唤起远程连接
```


## 输入服务器的 ip 地址

- 账号：`wineuser`
- 密码：`ethanyep`

![image](https://github.com/iszmxw/ocr/assets/31272102/d0ec322b-8aa9-4e35-8b91-266be22a73da)

## 如图进入到相应的目录，双击 `main.py` 运行

<img width="1510" alt="image" src="https://github.com/iszmxw/ntchat-api/assets/31272102/e757438a-2399-452c-b09f-e6502f4ef254">

## 或者用命令行运行

```bash
wine ~/ntchat@0.1.13/fastapi_example/main.py
```

## 看到下图就表示运行成功

<img width="1512" alt="image" src="https://github.com/iszmxw/ntchat-api/assets/31272102/dc26017d-e21f-4d35-97fc-b4d14041336a">
<img width="1512" alt="image" src="https://github.com/iszmxw/ntchat-api/assets/31272102/d41ce6f4-71c2-4008-ab7c-d78bde317147">


## 打开浏览器访问文档

输入 http://ip:8000/docs ，你会看到如下

<img width="1512" alt="image" src="https://github.com/iszmxw/ntchat-api/assets/31272102/5cddfecd-1b03-45a7-aa48-1b1702cecfa5">







