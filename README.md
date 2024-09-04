# architecture
The architecture documentation of project 'RoktoJog'

Certainly! Below is a high-level system diagram that outlines the key components and interactions for your blood donation platform.

Slide: https://docs.google.com/presentation/d/1etLFJ5n5DtjjVsJagSBV2QZ0oFbr6CA6slLQ_i2HF7M/edit?usp=sharing

### High-Level System Diagram

```plaintext
+-------------------+       +-----------------+      +-----------------+        +------------------+
|                   |       |                 |      |                 |        |                  |
|    Mobile App /   |<----->|   API Gateway   |<---->|    Backend      |<------>|  Database        |
|    Web Client     |       |                 |      |    Server       |        |  (MongoDB /      |
|  (React, Vue.js)  |       | (RESTful APIs)  |      |  (Node.js /     |        |  PostgreSQL)     |
|                   |       |                 |      |  Express.js)    |        |                  |
+-------------------+       +-----------------+      +-----------------+        +------------------+
       |                                   |                   |                          |
       v                                   |                   v                          v
+------------------+               +---------------+    +---------------+         +------------------+
|                  |               |               |    |               |         |                   |
| Notification     |<--------------| Authentication|    |  Blood Request|         |   User Profiles   |
| System (Twilio,  |               |  Service      |    |  Management   |         |  (Donor, Receiver,|
|  Firebase)       |               |               |    |               |         |  Organization)    |
|                  |               |               |    |               |         |                   |
+------------------+               +---------------+    +---------------+         +------------------+
       |                                                                                   |
       v                                                                                   v
+------------------+                                                                +-------------------+
|                  |                                                                |                   |
|   SMS, Email,    |                                                                |   Analytics and   |
|   Push Notifs    |                                                                |   Reporting       |
|                  |                                                                |                   |
+------------------+                                                                +-------------------+
```

### Components:

1. **Mobile App / Web Client:**
   - **Frontend:** Built with React, Vue.js, or Angular, providing a user interface for donors, recipients, and voluntary organizations.
   - **Interactions:** Allows users to register, log in, request blood, and view notifications.

2. **API Gateway:**
   - **RESTful APIs:** Manages communication between the frontend and backend services.
   - **Security:** Ensures secure data transmission with HTTPS and JWT tokens for authentication.

3. **Backend Server:**
   - **Framework:** Node.js with Express or Django/Rails for handling core business logic.
   - **Services:** Includes Blood Request Management, Notification System, and User Management.

4. **Database:**
   - **Database Choices:** MongoDB or PostgreSQL for storing user profiles, blood requests, and donation history.
   - **Data Models:** User profiles (Donors, Recipients, Organizations), Blood Requests, Donation Records.

5. **Notification System:**
   - **Services:** Integrates with Twilio for SMS/WhatsApp and Firebase for push notifications.
   - **Triggers:** Sends notifications based on blood requests, donor availability, and organization requirements.

6. **Authentication Service:**
   - **User Authentication:** Handles user login, registration, and role-based access control.
   - **Security:** JWT tokens for session management and secure access.

7. **Blood Request Management:**
   - **Request Flow:** Manages the lifecycle of blood requests, from creation to fulfillment.
   - **Matching Engine:** Finds suitable donors based on blood type, location, and last donation date.

8. **User Profiles:**
   - **Types:** Donor, Recipient, Voluntary Organization.
   - **Details:** Blood group, location, contact info, donation history, etc.

9. **Analytics and Reporting:**
   - **Dashboard:** Provides insights into the number of requests, donations, and success rates.
   - **Reports:** Helps organizations track their impact and optimize their efforts.

### Communication Flow:

1. **User Interaction:** Users interact with the platform via the Mobile App or Web Client.
2. **API Requests:** The frontend communicates with the Backend Server through the API Gateway.
3. **Data Processing:** The backend processes requests, accesses the database, and manages user profiles, blood requests, and notifications.
4. **Notification Dispatch:** The Notification System sends out SMS, emails, and push notifications to relevant users.
5. **Data Storage:** All data is stored securely in the Database, accessible to the backend services.

This system diagram should help you visualize the structure of your platform. If you need further details or refinements, feel free to ask!
