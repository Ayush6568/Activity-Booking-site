# Activity Booking App API

A RESTful API for booking various activities like cricket, movies, football matches, etc.

## Features

- User registration and authentication with JWT
- List available activities
- Book activities
- View personal bookings
- Input validation
- Password hashing
- Protected routes

## Tech Stack

- Node.js
- Express.js
- MongoDB
- JWT Authentication
- Express Validator
- Bcrypt

## Prerequisites

- Node.js (v14 or higher)
- MongoDB (local or Atlas)
- npm or yarn

## Setup Instructions

1. Clone the repository:
```bash
git clone <repository-url>
cd activity-booking-app
```

2. Install dependencies:
```bash
npm install
```

3. Create a `.env` file in the root directory with the following variables:
```
PORT=3000
MONGODB_URI=mongodb://localhost:27017/activity-booking
JWT_SECRET=your_jwt_secret_key_here
JWT_EXPIRE=24h
```

4. Start the server:
```bash
npm start
```

For development with auto-reload:
```bash
npm run dev
```

## API Endpoints

### Authentication

- `POST /api/auth/register` - Register a new user
  - Body: `{ name, email, phone, password }`

- `POST /api/auth/login` - Login user
  - Body: `{ email, password }`

### Activities

- `GET /api/activities` - Get all activities (public)
- `POST /api/activities` - Create new activity (protected)
  - Body: `{ title, description, location, dateTime }`

### Bookings

- `POST /api/bookings` - Book an activity (protected)
  - Body: `{ activityId }`

- `GET /api/bookings/my-bookings` - Get user's bookings (protected)

## Authentication

Protected routes require a JWT token in the Authorization header:
```
Authorization: Bearer <token>
```

## Error Handling

The API uses proper error handling and validation:
- Input validation using express-validator
- Proper error messages for invalid inputs
- JWT authentication errors
- MongoDB errors

## Security Features

- Password hashing using bcrypt
- JWT token-based authentication
- Protected routes
- Input validation and sanitization
