# Focus_write_server
C语言集中写Server的demo

## 运行方法：
```
g++ main.cpp -o main	//生成目标文件
./main ip port filename		//自行修改参数
```
## 原理：
绑定ip和端口监听连接并且检查目标文件名属性，无误后将文件内容读取到file_buf中和http_header一起发送到客户端，过程中iovec地址是连续的，再利用strlen可以计算出偏移量从而集中写入缓冲区或者说写入字节流中
