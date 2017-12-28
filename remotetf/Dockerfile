############################################
# version : godcong/remotepy:latest
# desc : 
############################################
#使用最新ubuntu镜像
FROM ubuntu:latest

#添加我的信息
MAINTAINER godcong (jumbycc@163.com)

RUN su

# 注意这里要更改系统的时区设置，因为在 web 应用中经常会用到时区这个系统变量，默认的 ubuntu 会让你的应用程序发生不可思议的效果哦
ENV DEBIAN_FRONTEND noninteractive

# 清空ubuntu更新包
#RUN rm -rf /var/lib/apt/lists/*

# 删除镜像节点，使用本地163节点替换
RUN rm -rf /etc/apt/sources.list
COPY sources.list /etc/apt/sources.list

# RUN apt-get update && apt-get install -y apt-utils

# RUN mkdir -p /root/.pip
ADD conf /root/.pip

# 添加rsa授权信息
ADD authorized /root/.ssh
#更换阿里云pip镜像地址
ADD conf /root/.ssh
#COPY docker /root/.ssh/id_rsa
#COPY docker.pub /root/.ssh/id_rsa.pub
#COPY docker.pub /root/.ssh/authorized_keys
RUN chmod 600 /root/.ssh/authorized_keys

# 一次性安装vim，wget，curl，ssh server等必备软件
RUN apt-get update && apt-get install -y --force-yes openssh-server sudo vim 
# 安装更新python pip
RUN apt-get install -y python3-pip python3-dev 
# 通过pip 安装 tensorflow
RUN pip3 install --upgrade pip tensorflow

RUN mkdir -p /var/run/sshd

# 将sshd的UsePAM参数设置成no
#RUN sed -i 's/UsePAM yes/UsePAM no/g' /etc/ssh/sshd_config
#RUN sed -i 's/PermitRootLogin prohibit-password/PermitRootLogin yes/g' /etc/ssh/sshd_config
#RUN sed -i 's/PermitEmptyPasswords yes/PermitEmptyPasswords no/g' /etc/ssh/sshd_config

EXPOSE 22
#sshd -D 非deamon模式运行
CMD ["/usr/sbin/sshd", "-D"]