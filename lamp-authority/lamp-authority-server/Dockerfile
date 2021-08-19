FROM openjdk:11-jre-slim
MAINTAINER zuihou 306479353@qq.com

RUN cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
    && echo "Asia/Shanghai" > /etc/timezone

#RUN apk update && apk upgrade && apk add ca-certificates && update-ca-certificates \
#    && apk add --update tzdata && cp /usr/share/zoneinfo/Asia/Shanghai /etc/localtime \
#    && echo "Asia/Shanghai" > /etc/timezone \
#    && rm -rf /var/cache/apk/*
#ENV TZ=Asia/Shanghai

ARG JAR_FILE
COPY ${JAR_FILE} /app.jar

ENTRYPOINT ["java", "-Xmx512m", "-Djava.security.egd=file:/dev/./urandom", "-Ddruid.mysql.usePingMethod=false", "-jar", "/app.jar"]
CMD ["--spring.profiles.active=docker"]
