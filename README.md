# Daily Commute Portal

A web application that helps users find and share daily commutes, making carpooling easier and more efficient.

## Features

- User authentication and authorization
- Create and manage daily commutes
- View available rides with detailed information
- Interactive map showing route details
- Real-time distance and duration calculations
- Join/leave rides with confirmation notifications

## Tech Stack

- Frontend:
  - React with TypeScript
  - Material-UI for components
  - Google Maps JavaScript API
  - Vite for build tooling

- Backend:
  - Node.js with Express
  - MongoDB for database
  - JWT for authentication
  - Google Maps Distance Matrix API

## Project Setup

### Prerequisites

- Node.js (v14 or higher)
- MongoDB
- Google Maps API key
- Google Maps Distance Matrix API key

### Environment Variables

Create a `.env` file in the root directory with the following variables:

```env
# MongoDB
MONGODB_URI=your_mongodb_uri

# JWT
JWT_SECRET=your_jwt_secret

# Google Maps
GOOGLE_MAPS_API_KEY=your_google_maps_api_key
GOOGLE_DISTANCE_MATRIX_API_KEY=your_distance_matrix_api_key
```

Create a `.env` file in the frontend directory:

```env
VITE_GOOGLE_MAPS_API_KEY=your_google_maps_api_key
```

### Installation

1. Clone the repository:
```bash
git clone https://github.com/SATYAM-TYAGI/Daily-Commute-Portal.git
cd Daily-Commute-Portal
```

2. Install backend dependencies:
```bash
cd backend
npm install
```

3. Install frontend dependencies:
```bash
cd ../frontend
npm install
```

4. Start the development servers:

Backend:
```bash
cd backend
npm run dev
```

Frontend:
```bash
cd frontend
npm run dev
```

The application will be available at:
- Frontend: http://localhost:5173
- Backend: http://localhost:3000

## API Endpoints

### Authentication

- `POST /api/auth/register`
  - Register a new user
  - Body: { username, password }

- `POST /api/auth/login`
  - Login user
  - Body: { username, password }

### Commutes

- `GET /api/commutes`
  - Get all available commutes
  - Query params: startLocation, endLocation, date

- `POST /api/commutes`
  - Create a new commute
  - Body: { startLocation, endLocation, date, departureTime, mode }

- `GET /api/commutes/:id`
  - Get a specific commute by ID

- `PUT /api/commutes/:id/join`
  - Join a commute
  - Body: { userId }

- `PUT /api/commutes/:id/leave`
  - Leave a commute
  - Body: { userId }

## Challenges and Solutions

1. **Google Maps Integration**
   - Challenge: Initializing the Google Maps API and handling route calculations
   - Solution: Created a custom hook to load the API asynchronously and implemented proper error handling

2. **Real-time Distance Calculations**
   - Challenge: Calculating accurate distances and durations for routes
   - Solution: Integrated Google Maps Distance Matrix API and cached results for better performance

3. **State Management**
   - Challenge: Managing complex state for selected rides and user interactions
   - Solution: Implemented React hooks and context for efficient state management

4. **Responsive Design**
   - Challenge: Creating a responsive layout for different screen sizes
   - Solution: Used Material-UI's Grid system and responsive breakpoints

## Deployment

The application can be deployed using various platforms:

### Frontend
- Vercel
- Netlify
- GitHub Pages

### Backend
- Heroku
- DigitalOcean
- AWS

## Contributing

1. Fork the repository
2. Create your feature branch (`git checkout -b feature/amazing-feature`)
3. Commit your changes (`git commit -m 'Add some amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.

## Acknowledgments

- Material-UI for the component library
- Google Maps Platform for mapping services
- MongoDB for the database solution
