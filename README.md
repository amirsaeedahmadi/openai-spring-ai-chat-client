# Simple Spring AI Chat Controller using OpenAI APIs

Web Programming Research Project

## Project Overview

This is a Spring Boot application that demonstrates how to create a chatbot with streaming capabilities using Spring AI and OpenAI gpt-4o model. It allows users to interact with the AI through both traditional request-response and streaming responses.

## Project Requirements

- Java 23
- Maven 3.6.3 or newer
- Spring Boot 3.3.4
- Spring AI 1.0.0-M2

## Dependencies

The project relies on the following key dependencies:

- `spring-boot-starter-web`: 
- `spring-ai-openai-spring-boot-starter`: 
- `spring-boot-starter-test`: 

## Getting Started

To get started with this project, ensure you have Java 23 and Maven installed on your system. Then, follow these steps:

1. Set up your OpenAI API key:

    - Export OpenAI API Key: 
        ```
        export OPEN_AI_API_KEY <your api key>
        ```
    - Locate `application.properties` in the `src/main/resources` directory

    - Specify that you want to use the gpt-4o-mini Model (or the model of your choice)
      ```
      spring.ai.openai.chat.options.model=gpt-4o-mini
      ```

2. Build the project:
   ```
   mvn clean install
   ```

3. Run the application:
   ```
   mvn spring-boot:run
   ```

The application will start, and you'll be able to access the chat endpoints.

## How to Run the Application

Once the application is running, you can interact with it using the following endpoints:

1. Traditional chat (POST request):
   ```
   POST http://localhost:8080/chat?message=Your message here
   ```

2. Streaming chat (GET request):
   ```
   GET http://localhost:8080/stream?message=Your message here
   ```

You can use tools like cURL, Postman, or create a simple frontend to interact with these endpoints. I like to use [httpie](https://httpie.io/) with the `--stream` option 

```
http --stream :8080/stream message=="What is web programming?"
```

