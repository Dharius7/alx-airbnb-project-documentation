# Airbnb Clone Backend - Feature Requirements

## 1. User Authentication

### Functional Requirements
- Users must be able to register as a guest or host.
- Secure login/logout functionality using JWT.
- OAuth integration (e.g., Google, Facebook) for social logins.

### API Endpoints
| Method | Endpoint          | Description            |
|--------|-------------------|------------------------|
| POST   | /api/auth/register | Register a new user    |
| POST   | /api/auth/login    | Log in with credentials|
| POST   | /api/auth/oauth    | Log in with OAuth      |

### Input/Output
**POST /api/auth/register**
```json
Input:
{
  "first_name": "John",
  "last_name": "Doe",
  "email": "john@example.com",
  "password": "SecurePass123"
}

Output:
{
  "token": "<jwt-token>",
  "user": {
    "id": "uuid",
    "role": "guest"
  }
}


Input:
{
  "name": "Beach House",
  "location": "Miami, FL",
  "price_per_night": 120.00,
  "description": "Oceanfront view",
  "amenities": ["WiFi", "Pool"]
}

Output:
{
  "property_id": "uuid",
  "host_id": "uuid",
  "created_at": "timestamp"
}


Input:
{
  "property_id": "uuid",
  "start_date": "2025-06-01",
  "end_date": "2025-06-05"
}

Output:
{
  "booking_id": "uuid",
  "status": "pending",
  "total_price": 480.00
}
