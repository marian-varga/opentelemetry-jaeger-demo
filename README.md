# opentelemetry-jaeger-demo
Hands-on exercise to try distributed tracing quickly without a complicated setup

Part of the sample code for Chapter 9 of the book _Mastering RESTful Web Services with Java_ (see: [love2integrate.com](https://love2integrate.com))

Make sure you have Java 21 or later installed.

Start Jaeger: `docker-compose up`

Build the application: `./mvnw package`

Start the application: `java -jar target/*.jar`

Send some requests to it using curl or other HTTP client:
```
curl -X PUT --header "Content-Type: application/json" -d '{  "name": "Keyboard",  "description": "Ergonomic Keyboard",  "price": 60 }' http://localhost:8080/api/products/AK12345
curl http://localhost:8080/api/products/AK12345
curl http://localhost:8080/api/products/AK12346
```

See the traces in Jaeger at http://localhost:16686/