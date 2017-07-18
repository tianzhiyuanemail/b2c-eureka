#基础镜像
FROM  frolvlad/alpine-oraclejdk8
#维护者的信息
MAINTAINER lgl "457900130@qq.com"
#更新 假设我们更新了apt-get源，下载，解压并安装了一些软件包，
#它们都保存在/var/lib/apt/lists/目录中。但是，运行应用时Docker镜像中并不需要这些文件。
#我们最好将它们删除，因为它会使Docker镜像变大##。
RUN apt-get update && rm -rf /var/lib/apt/lists/*
#复制当前目录jdk
#COPY jdk1.8.0_131 jdk1.8.0_131
#复制项目jar
ADD   b2c-eureka-0.0.1-SNAPSHOT.jar  app.jar
#指定环境变量，会被RUN指令使用，并在容器运行时保存
#ENV JAVA_HOME /jdk1.8.0_131
#ENV PATH $JAVA_HOME/bin:$PATH
#ENV CLASSPATH .:$JAVA_HOME/lib
#对外开放端口
EXPOSE 8761
#配置容器启动后执行的命令，并且不可被 docker run 提供的参数覆盖。（每个 Dockerfile 中只能有一个 ENTRYPOINT(一般运行脚本) ，当指定多个时，只有最后一#个起效）
CMD ["java","-jar","/app.jar"]