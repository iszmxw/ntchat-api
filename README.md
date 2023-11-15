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

### 容器的准备工作已经完成了，开始进入容器



