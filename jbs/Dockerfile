############################################
# version : godcong/jbs:latest
# desc : 
############################################
#使用最新alpine镜像
FROM alpine:latest

#添加我的信息
MAINTAINER godcong (jumbycc@163.com)

COPY ./IntelliJIDEALicenseServer/IntelliJIDEALicenseServer_linux_amd64 /home/jbs

EXPOSE 1027

#sshd -D 非deamon模式运行
CMD ["/home/jbs"]