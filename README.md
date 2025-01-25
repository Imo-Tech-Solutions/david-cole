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

