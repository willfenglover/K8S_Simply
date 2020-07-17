1. gitRepo基于emptyDir，在pod启动时(容器启动之前)会检出git代码特定版本到卷中
当git有提交时，gitRepo不会拉取新的代码，需要删除pod触发新建新的pod才行

2. 创建Pod并添加转发
kubectl create -f gitrepo-volume-pod.yaml
kubectl port-forward --address 0.0.0.0 gitrepo-volume-pod 8082:80


