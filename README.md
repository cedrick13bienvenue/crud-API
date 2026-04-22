# crud-API

A modular RESTful API built with Flask for managing moto taxi bookings in Kigali, Rwanda.

## 🚀 Features

- Full CRUD operations for bookings
- RESTful API design
- Interactive Swagger/OpenAPI documentation
- Modular architecture with separation of concerns
- CORS support
- JSON data persistence

## 📁 Project Structure

```
.
├── app.py                      # Application entry point
├── requirements.txt            # Python dependencies
├── config/
│   └── config.py              # Configuration settings
├── models/
│   └── booking.py             # Data models and schemas
├── services/
│   └── booking_service.py     # Business logic layer
├── routes/
│   └── booking_routes.py      # API endpoints and routes
└── data/
    └── data.json              # JSON database
```

## 🛠️ Setup

1. **Create a virtual environment** (recommended):

   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

2. **Install dependencies**:

   ```bash
   pip install -r requirements.txt
   ```

3. **Run the application**:
   ```bash
   python app.py
   ```

The API will start at `http://127.0.0.1:8000`

## 📚 API Documentation

Interactive Swagger documentation is available at:

```
http://127.0.0.1:8000/docs
```

## 🔌 API Endpoints

Base URL: `http://127.0.0.1:8000/api/v1`

### Get All Bookings

```bash
GET /api/v1/bookings/
```

### Get Booking by ID

```bash
GET /api/v1/bookings/{id}
```

### Create New Booking

```bash
POST /api/v1/bookings/
Content-Type: application/json

{
  "customer_name": "John Doe",
  "pickup": "Kigali City Center",
  "destination": "Airport",
  "fare": 3000,
  "status": "pending"
}
```

### Update Booking

```bash
PUT /api/v1/bookings/{id}
Content-Type: application/json

{
  "status": "confirmed",
  "fare": 2500
}
```

### Delete Booking

```bash
DELETE /api/v1/bookings/{id}
```

## 📊 Data Model

| Field         | Type    | Required | Description                                            |
| ------------- | ------- | -------- | ------------------------------------------------------ |
| id            | integer | auto     | Unique identifier                                      |
| customer_name | string  | yes      | Customer's name                                        |
| pickup        | string  | yes      | Pickup location                                        |
| destination   | string  | yes      | Destination location                                   |
| fare          | integer | yes      | Fare amount in RWF                                     |
| status        | string  | yes      | Booking status (pending/confirmed/completed/cancelled) |

## 🧪 Example Usage with curl

**Create a booking:**

```bash
curl -X POST http://127.0.0.1:8000/api/v1/bookings/ \
  -H "Content-Type: application/json" \
  -d '{
    "customer_name": "Jane Smith",
    "pickup": "Remera",
    "destination": "Kimironko",
    "fare": 1200,
    "status": "pending"
  }'
```

**Get all bookings:**

```bash
curl http://127.0.0.1:8000/api/v1/bookings/
```

**Update a booking:**

```bash
curl -X PUT http://127.0.0.1:8000/api/v1/bookings/1 \
  -H "Content-Type: application/json" \
  -d '{"status": "completed"}'
```

**Delete a booking:**

```bash
curl -X DELETE http://127.0.0.1:8000/api/v1/bookings/1
```

## 🏗️ Architecture

- **app.py**: Application factory and initialization
- **config/**: Configuration management
- **models/**: Data models and schema definitions
- **services/**: Business logic and data operations
- **routes/**: API endpoints and request handling
- **data/**: JSON file storage

## 🔧 Configuration

Edit `config/config.py` to modify:

- Server host and port
- Data file location
- Debug mode
- Environment-specific settings

## 📝 License

MIT License

---
