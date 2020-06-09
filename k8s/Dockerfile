FROM openjdk:8-jdk-alpine

# set environment
ENV BASE_DIR="/nacos" \
	CLUSTER_CONF="/nacos/conf/cluster.conf"

WORKDIR /$BASE_DIR

ADD target/nacos-server.jar nacos-server.jar
ADD bin/startup.sh startup.sh
ADD ../config config
ADD ../conf /conf

#设置容器时间
RUN ln -snf /usr/share/zoneinfo/Asia/Shanghai /etc/localtime && echo Asia/Shanghai > /etc/timezone

EXPOSE 8848

#指定容器启动程序及参数   <ENTRYPOINT> "<CMD>"
ENTRYPOINT ["/nacos/startup.sh"]
