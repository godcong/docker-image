############################################
# version : godcong/kms:latest
# desc : 
############################################
#使用最新alpine镜像
FROM alpine:latest

#添加我的信息
MAINTAINER godcong (jumbycc@163.com)

COPY ./vlmcsd /home/vlmcsd

EXPOSE 1688

ENTRYPOINT ["/home/vlmcsd", "-D", "-e"]