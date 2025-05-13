# Search Engine Backend

A robust and scalable search engine backend built with Spring Boot, featuring web crawling, indexing, and search capabilities.

## Technologies Used

### Core Technologies

- **Spring Boot 2.5.2**: Main framework for building the application
- **Java 11**: Programming language
- **Maven**: Build and dependency management

### Data Storage & Processing

- **Redis**

  - Primary caching layer for storing search results and frequently accessed data
  - Used for temporary storage of crawled pages before processing
  - Implements rate limiting and session management
  - Provides fast in-memory access to frequently used data
  - Stores inverted index for quick search operations

- **Kafka**
  - Message broker for handling asynchronous processing
  - Manages the crawling queue and processing pipeline
  - Ensures reliable delivery of crawl tasks
  - Enables horizontal scaling of crawler instances
  - Maintains processing order and fault tolerance
  - Handles high-throughput data streaming between components

### API & Documentation

- **Spring Web**: RESTful API implementation
- **Swagger/Springfox**: API documentation and testing interface

## Architecture

The search engine backend consists of several key components:

1. **Web Crawler**

   - Crawls and indexes web pages
   - Extracts relevant content and metadata
   - Stores data in Redis for quick access
   - Uses Kafka for task distribution and processing

2. **Message Processing**

   - Uses Kafka for asynchronous processing
   - Handles crawling tasks and indexing operations
   - Ensures scalability and fault tolerance
   - Manages the flow of data between components

3. **Search API**
   - RESTful endpoints for search operations
   - Swagger documentation for API testing
   - Efficient query processing and result ranking
   - Leverages Redis for fast result retrieval

## Getting Started

### Prerequisites

- Java 11 or higher
- Maven
- Docker and Docker Compose

### Running the Application

1. Start the required services using Docker Compose:

   ```bash
   docker-compose up -d
   ```

   This will start:

   - Kafka and Zookeeper for message processing
   - Redis server for caching and data storage

2. Build and run the application:

   ```bash
   mvn clean install
   mvn spring-boot:run
   ```

3. Access the API documentation:
   - Swagger UI: `http://localhost:8080/swagger-ui.html`

## Project Structure

```
src/main/java/com/handson/searchengine/
├── config/         # Configuration classes
├── controller/     # REST API endpoints
├── crawler/        # Web crawling implementation
├── kafka/          # Kafka message handling
├── model/          # Data models
└── util/           # Utility classes
```

## Features

- Web page crawling and indexing
- Real-time search capabilities
- Distributed processing with Kafka
- Redis-based caching for improved performance
- Asynchronous processing of crawl tasks
- RESTful API for search operations
- API documentation with Swagger


# Acknowledgments

This project was developed as part of the Hands-On Programming course by Niv Itzhaki. Through this experience, I had the opportunity to explore many amazing technologies and gain practical knowledge in backend development, security, testing, and DevOps. Huge thanks to Niv Itzhaki for the guidance and support throughout the course!