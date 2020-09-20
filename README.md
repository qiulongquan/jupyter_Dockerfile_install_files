```
这个是 jupyter Dockerfile 的安装文件

包括 2 个 dockerfile
一个是 jupyter_tensorflow(镜像文件中已经包括了需要的库文件)
一个是 jupyter_data_scientist(镜像文件中已经包括了需要的库文件)

Note that:
如果在jupyter里面出现权限问题导致不能修改文件或者增加文件问题，使用下面的命令重新进入jupyter
-e NB_UID=$(id -u) --user root这个应该是配置用户为root
docker run -d -p 8888:8888 -e NB_UID=$(id -u) --user root -v /home/ec2-user/jupyter_experiments:/work  jupyter_tensorflow:1.0

```
