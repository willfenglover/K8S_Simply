emptyDir用于容器之间共享文件实践

1. 实践内容
目的：构建一个仅有web服务器容器代理和单独HTML的卷的pod
描述：使用Nginx作为web服务器，UNIX fortune命令生成HTML内容
      将这两个镜像运行到同一个pod中，并共用一个卷

操作：
1. 启动容器
kubectl create -f fortune-pod.yaml
2. 开启8081到pod的80端口
kubectl port-forward --address 0.0.0.0 fortune 8081:80

效果：
html-generator容器每隔10s会生成新的内容到index.html
web-server容器会将当前的fortune响应给客户端

YAML解析：
1. emptyDir的文件存储在内存中，默认是存储到工作节点的磁盘 
emptyDir: 
     medium: Memory


