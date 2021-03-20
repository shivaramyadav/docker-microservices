FROM maven as build
WORKDIR /app
COPY . .
RUN mvn install

FROM openjdk-8-jdk
WORKDIR /app
COPY --from=build /app/target/offers-0.01-SNAPSHOT.jar /app
EXPOSE 1001
CMD ["java","-jar","offers-0.01-SNAPSHOT.jar"]
