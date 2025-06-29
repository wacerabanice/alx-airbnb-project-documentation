# 🧱 alx-airbnb-project-documentation

A list of all the features and functionalities the backend needs to support. This includes user authentication, property management, booking system, and payments.

👤 User Authentication & Roles
User registration & login (email + password)
Password hashing and security

Role-based access control:
guest: can search and book properties
host: can list and manage properties
admin: system oversight (optional)

| Feature                          | Description                                                                      |
| -------------------------------- | -------------------------------------------------------------------------------- |
| **Sign Up**                      | New users register with email, password, role (guest/host/admin), and basic info |
| **Login**                        | Users log in via email and password                                              |
| **Role-Based Access Control**    | Permissions based on role (e.g., host can manage properties)                     |
| **Password Hashing**             | Securely store user passwords (e.g., bcrypt)                                     |
| **Session / JWT Authentication** | Token-based auth for secure API access                                           |
| **Forgot Password / Reset**      | Email-based reset functionality                                                  |
| **Profile Management**           | View and update profile information                                              |


🏘️ Property Management (Host)
Create, update, and delete listings
Add descriptions, price, location
View host’s own listings


| Feature                      | Description                                          |
| ---------------------------- | ---------------------------------------------------- |
| **Create Property**          | Hosts can add new property listings                  |
| **Edit Property**            | Hosts can update property details                    |
| **Delete Property**          | Hosts can remove a listing                           |
| **View All Properties**      | Fetch all properties (for guests, search, filters)   |
| **Search/Filter Properties** | Based on location, price, availability, rating, etc. |
| **Upload Images (optional)** | Attach images to property (via file storage service) |


📅 Booking System (Guest)
Search available properties by location and date
Create a booking request
View and manage booking status (pending, confirmed, canceled)
Cancel a booking

| Feature                  | Description                                         |
| ------------------------ | --------------------------------------------------- |
| **Book Property**        | Guests book a property with start & end dates       |
| **Availability Check**   | Prevent double bookings (date overlap detection)    |
| **Cancel Booking**       | Guests or hosts can cancel a booking                |
| **View Booking History** | Guest and host booking records                      |
| **Booking Status**       | Status tracking: `pending`, `confirmed`, `canceled` |


💳 Payment System
Make payment for confirmed bookings
Store payment method: credit_card, paypal, stripe
View payment history

| Feature                          | Description                                |
| -------------------------------- | ------------------------------------------ |
| **Make Payment**                 | Guests can pay via supported methods       |
| **Payment Methods**              | Supports `credit_card`, `paypal`, `stripe` |
| **Link to Booking**              | Payments linked to specific bookings       |
| **Payment History**              | Track user payment history                 |
| **Automatic Invoice Generation** | Optional PDF/email receipts per payment    |


⭐ Reviews (Guests)
Submit reviews (rating + comment)
Only allowed after a completed booking

| Feature                | Description                         |
| ---------------------- | ----------------------------------- |
| **Add Review**         | Guests leave reviews for properties |
| **Rating System**      | 1–5 star rating, validated          |
| **View Reviews**       | Public and host-visible feedback    |
| **Prevent Duplicates** | One review per booking/user         |


💬 Messaging (Guests ↔ Hosts)
Send and receive messages
View message history


| Feature                          | Description                                |
| -------------------------------- | ------------------------------------------ |
| **Send Message**                 | User-to-user direct messaging              |
| **Inbox View**                   | List all received messages                 |
| **Outbox View**                  | List all sent messages                     |
| **Timestamped Threads**          | Show conversations in order                |
| **Delete Message (soft delete)** | Optional message removal from inbox/outbox |


### ⚙️ 7. **Admin Controls**

| Feature                 | Description                                     |
| ----------------------- | ----------------------------------------------- |
| **View All Users**      | Admin can view and filter all users             |
| **Manage Properties**   | Admin can delete or flag inappropriate listings |
| **Manage Bookings**     | Oversee active/pending bookings                 |
| **Manage Payments**     | Monitor or resolve payment issues               |
| **Suspend Users/Hosts** | Enforce platform rules                          |



### 🖥️ 8. **System & Integration Features**

| Feature                       | Description                                              |
| ----------------------------- | -------------------------------------------------------- |
| **API Endpoints**             | RESTful endpoints for all modules                        |
| **Rate Limiting**             | Prevent abuse of login, booking, etc.                    |
| **Logging & Monitoring**      | Track errors, user actions (e.g., via Sentry, ELK)       |
| **Database Indexing**         | Optimize performance on foreign keys, email, booking\_id |
| **Environment Configuration** | Separate dev/staging/prod settings                       |


![Airbnb Backend Features](airbnbBackendFeatures.png)

