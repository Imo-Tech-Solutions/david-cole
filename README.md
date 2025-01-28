# Technical Interview Problem: Scalable Messaging System

## **Problem Description**

You are tasked with designing and implementing a scalable backend for a messaging system similar to WhatsApp or Slack. The system must allow users to send, receive, and retrieve messages efficiently while ensuring scalability and reliability as the user base grows.

---

## **Requirements**

### **1. Core Features**

1. **Send a Message**

   - Endpoint: `POST /messages`
   - Accepts:
     - Sender ID
     - Receiver ID (or Group ID for group messages)
     - Message content
     - Timestamp
   - Stores the message in a database.

2. **Retrieve Messages**

   - Endpoint: `GET /messages`
   - Features:
     - Fetch messages between two users or within a group.
     - Support pagination for message history.
     - Allow filtering by a date range.

3. **Delivery Status**
   - Track message status: `sent`, `delivered`, and `read`.
   - Update status when a recipient reads the message.

### **2. Database Design**

Design a schema to store:

- Users
- Messages
- Groups (if applicable)
- Delivery status of each message.

Ensure the schema supports:

- Fast retrieval of conversation history.
- Efficient storage for large-scale systems.

### **3. Scalability Considerations**

- Support millions of users and billions of messages.
- Implement a caching layer (e.g., Redis) for frequently accessed data.
- Use database sharding or partitioning for scalability.
- Propose strategies for load balancing and failover.

### **4. Real-time Notifications**

- Use WebSockets or a similar protocol for real-time communication.

---

## **Technical Deliverables**

1. **API Implementation**

   - Create fully functional RESTful API endpoints for the core features.
   - Validate all inputs and handle errors gracefully.

2. **Database Design**

   - Provide the schema definition (SQL or NoSQL) for the system.

3. **Caching Strategy**

   - Integrate a caching layer for optimizing message retrieval and user status.

4. **Documentation**

   - Provide a `README.md` explaining:
     - How to set up and run the application.
     - The architecture and design decisions.

5. **Dockerization**
   - Create a `Dockerfile` to containerize the application.
   - Provide a `docker-compose.yml` to set up the application, database, and caching layer.

---

## **Evaluation Criteria**

1. **Code Quality:**

   - Adherence to clean code practices and readability.

2. **Scalability and Performance:**

   - Efficient database queries and caching implementation.

3. **Functionality:**

   - Correct implementation of API endpoints and real-time notifications.

4. **Documentation:**
   - Clarity and completeness of the provided documentation.

## Prerequisites

Before running the system, make sure you have the following installed:

- **Docker**: For containerizing the application and services.
- **Docker Compose**: To manage multi-container Docker applications.
- **Node.js** (optional, if you're running the backend manually without Docker).

## Setting Up the Environment

### 1. Clone the Repository

First, clone the repository to your local machine:

```
git clone https://github.com/Imo-Tech-Solutions/david-cole.git
cd david-cole
```

### 2. Environment Variables

You can configure the application by modifying the .env.sample or create a new .env file, also set environment variables in the docker-compose.yml file.

PORT: The port on which the app will run. Default is 3000.
DB_USER: add your postgres username.
DB_PASSWORD: add your postgres password.
DB_HOST: add your postgres hostname. (use: "db" for Docker).
REDIS_HOST: The Redis host (default: redis for Docker).
REDIS_PORT: The Redis port (default: 6379).

### 2. Docker Setup

This system uses Docker to manage the backend services like PostgreSQL and Redis. To run the application, use Docker Compose to start all services.

Build and Run with Docker Compose:
Run the following command to start the system with all dependencies:

```
docker-compose up --build
```

This will:

Build the Docker containers.
Start the app container (the messaging system).
Start the PostgreSQL container (for database storage).
Start the Redis container (for caching and real-time messaging).

### 4. Testing the System

Once the system is running, you can test the functionality by making HTTP requests to
`POST http://localhost:3000/api/v1/messages` to add new messages
`GET http://localhost:3000/api/v1/messages` to retrieve messages
`Web socket on ws://localhost:3000` to observe real time messaging
