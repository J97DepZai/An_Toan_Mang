# Phase 1: Biên dịch code Java bằng Maven & JDK 17
FROM maven:3.9.6-eclipse-temurin-17 AS build
WORKDIR /app

# Copy file cấu hình Maven và tải thư viện
COPY pom.xml .
RUN mvn dependency:go-offline -B

# Copy mã nguồn và đóng gói file .jar
COPY src ./src
RUN mvn clean package -DskipTests

# Phase 2: Chạy ứng dụng bằng JDK Runtime nhẹ
FROM eclipse-temurin:17-jre
WORKDIR /app
COPY --from=build /app/target/*.jar app.jar

EXPOSE 8080
ENTRYPOINT ["java", "-jar", "app.jar"]