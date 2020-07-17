fortuneloop.sh脚本会每隔10s输出文件到/var/htdocs/index.html

在该目录，执行以下两条命令，打包镜像至公司内部镜像仓库Harbor
  docker build -t cr.souche-inc.com/fw/fortune .
  docker push cr.souche-inc.com/fw/fortune
