
## 📄 Backend Requirement Specifications

### 1. ✅ **User Authentication**

#### 🔧 Feature Description

Handles user registration, login, and role-based access control (guest, host, admin).

#### 🔗 API Endpoints

| Method | Endpoint             | Description         |
| ------ | -------------------- | ------------------- |
| POST   | `/api/auth/register` | Register a new user |
| POST   | `/api/auth/login`    | Authenticate user   |
| GET    | `/api/user/me`       | Get user profile    |

#### 🔤 Input/Output

* **POST `/register`**

  * **Input**: `{ first_name, last_name, email, password, role }`
  * **Output**: `201 Created`, `{ user_id, email, role }`
* **POST `/login`**

  * **Input**: `{ email, password }`
  * **Output**: `200 OK`, `{ token, user_id, role }`
* **GET `/me`**

  * **Auth Required**
  * **Output**: `{ user_id, name, email, role }`

#### ✅ Validation Rules

* Email: valid format, unique
* Password: minimum 8 characters
* Role: must be `guest`, `host`, or `admin`

#### ⚙️ Performance Criteria

* Response time < 200ms
* Token generation within 100ms
* Concurrent logins handled securely

---

### 2. 🏡 **Property Management**

#### 🔧 Feature Description

Allows hosts to create, update, and delete property listings.

#### 🔗 API Endpoints

| Method | Endpoint              | Description             |
| ------ | --------------------- | ----------------------- |
| POST   | `/api/properties`     | Create new property     |
| GET    | `/api/properties/:id` | View property details   |
| PUT    | `/api/properties/:id` | Update property listing |
| DELETE | `/api/properties/:id` | Remove property listing |

#### 🔤 Input/Output

* **POST `/properties`**

  * **Input**: `{ name, description, location, pricepernight }`
  * **Output**: `201 Created`, `{ property_id, name, pricepernight }`
  * **PUT `/properties/:id`**

  * **Input**: `{ updated fields }`
  * **Output**: `200 OK`, `{ updated_property }`

#### ✅ Validation Rules

* Price must be positive decimal
* Name/location/description: non-empty
* Only hosts can create/update/delete

#### ⚙️ Performance Criteria

* Listing retrieval in < 250ms
* Full-text search on `location` and `name`

---

### 3. 📆 **Booking System**

#### 🔧 Feature Description

Allows guests to book properties, cancel, and view booking history.

#### 🔗 API Endpoints

| Method | Endpoint             | Description          |
| ------ | -------------------- | -------------------- |
| POST   | `/api/bookings`      | Create a booking     |
| GET    | `/api/bookings/user` | List user's bookings |
| DELETE | `/api/bookings/:id`  | Cancel a booking     |

#### 🔤 Input/Output

* **POST `/bookings`**

  * **Input**: `{ property_id, start_date, end_date }`
  * **Output**: `{ booking_id, status, total_price }`
* **GET `/bookings/user`**

  * **Output**: `[ { booking_id, property, date_range, status } ]`

#### ✅ Validation Rules

* No overlapping bookings
* Dates must be in the future
* End date must be after start date

#### ⚙️ Performance Criteria

* Booking creation under 300ms
* Availability check within 100ms
* Accurate total price calculation
