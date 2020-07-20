该案例简单演示ENTRYPOINT和CMD的区别

ENTRYPOINT：定义容器启动时调用的可执行程序

CMD：传递给ENTRYPOINT的参数

docker build -t cr.souche-inc.com/fw/fortune:args

docker push cr.souche-inc.com/fw/fortune:args

docker run -it cr.souche-inc.com/fw/fortune:args

docker run -it cr.souche-inc.com/fw/fortune:args 3



