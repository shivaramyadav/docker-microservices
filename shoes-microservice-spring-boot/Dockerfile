FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk-8-jdk
WORKDIR /app
COPY --from=build /app/target/shoes-0.01-SNAPSHOT.jar /app
EXPOSE 1002
CMD ["java","-jar","shoes-0.01-SNAPSHOT.jar"]
