# docker-image

# remotetf #
ubuntu镜像更换为cn镜像环境
pip镜像更换为aliyun镜像环境

TensorFlow远程开发环境使用方法：
将 id_rsa.pub 复制到 keys 目录下 并 重命名 为 authorized_keys
执行
> docker-compose up -d
自动建立docker开发环境

配置pycharm：
参照pycharm ssh 远程开发
ps: root目录选择/home