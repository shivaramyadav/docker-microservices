FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk-8-jdk
WORKDIR /app
COPY --from=build /app/target/zuul-0.01-SNAPSHOT.jar /app
EXPOSE 9999
CMD ["java","-jar","zuul-0.01-SNAPSHOT.jar"]
