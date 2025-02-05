FROM maven:3.8.4-openjdk-17 as build
RUN groupadd -r mygroup && useradd -r -g mygroup -m -d /home/myuser myuser
USER myuser
#ARG JAR_FILE= target/*.jar
COPY target/*.jar app.jar
EXPOSE 8080
ENTRYPOINT [ "java","-jar","/app.jar" ]
# WORKDIR /home/myuser/workspace/app
# COPY pom.xml .
# COPY src src
# RUN mvn clean install -DskipTests
# RUN mkdir -p target/dependency && (cd target/dependency ; jar -xf ../*.jar)
# FROM openjdk:22-ea-22
# VOLUME /tmp
# ARG DEPENDENCY=home/myuser/workspace/app/target/dependency
# COPY --from=build ${DEPENDENCY}/BOOT-INF/lib /app/lib
# COPY --from=build ${DEPENDENCY}/META-INF /app/META-INF
# COPY --from=build ${DEPENDENCY}/BOOT-INF/classes /app
# COPY --from=build ${DEPENDENCY}/BOOT-INF/classes/application.properties /app/application.properties
# COPY --from=build /home/myuser/workspace/app/src/main/resources/mysql-connector-java-*.jar /app/lib/mysql-connector-java.jar
# ENTRYPOINT ["java","-cp","app:app/lib/*", "com.bezkoder.spring.datajpa.SpringBootDataJpaApplication"]