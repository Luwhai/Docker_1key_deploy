# 阶段1：获取源代码
# FROM alpine/git AS source
# WORKDIR /src
# ARG GITEA_URL=http://192.168.80.133:3000/b00128/crmeb_front.git
# ARG GIT_BRANCH=main
# RUN git clone --branch ${GIT_BRANCH} --depth 1 ${GITEA_URL} .

# 阶段2：构建阶段
# FROM maven:3.8-openjdk-17 AS builder
# WORKDIR /app
# COPY pom.xml .
# RUN mvn dependency:go-offline
# COPY --from=source ./src
# RUN mvn clean package -DskipTests
 
# 阶段3：运行阶段
FROM eclipse-temurin:17-jre-alpine
RUN apk add fontconfig ttf-dejavu

WORKDIR /app
COPY admin.jar app.jar

COPY crmebimage/ crmebimage/

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]