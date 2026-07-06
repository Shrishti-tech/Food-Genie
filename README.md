# Food Genie

Deployed project :https://genie-food-app.netlify.app/

Food Genie is a MERN stack food ordering application with restaurant browsing, menus, user authentication, cart management, order placement, Stripe checkout, Cloudinary image support, coupons, and AI-assisted food/review features.

## Tech Stack

- Frontend: React, Vite, Redux Toolkit, React Router, Axios
- Backend: Node.js, Express.js, MongoDB, Mongoose
- Services: Cloudinary, Stripe, Nodemailer, Groq AI
- Authentication: JWT with cookies

## Features

- User signup, login, logout, profile, and profile update
- Restaurant listing, search, sorting, and veg-only filter
- Admin restaurant, menu, and food item management
- Cart add, update quantity, and remove item
- Order creation and order history
- Stripe checkout integration
- Coupon support
- Cloudinary image configuration
- AI-generated food descriptions and review analysis

## Project Structure

```text
Food Genie/
  backend/
    app.js
    server.js
    config/
    controllers/
    models/
    routes/
    services/
    utils/
  frontend/
    src/
    public/
    vite.config.js
```

## Prerequisites

- Node.js
- npm
- MongoDB Atlas or local MongoDB
- Cloudinary account
- Stripe account
- Groq API key, if using AI features

## Environment Variables

Create this file:

```text
backend/config/config.env
```

Use the example file as a template:

```text
backend/config/config.env.example
```

Required variables:

```env
PORT=4000
NODE_ENV=DEVELOPMENT

DB_LOCAL_URI=your_mongodb_connection_string
JWT_SECRET=your_jwt_secret
JWT_EXPIRE=7d
JWT_EXPIRES_TIME=7d

CLOUDINARY_CLOUD_NAME=your_cloudinary_cloud_name
CLOUDINARY_API_KEY=your_cloudinary_api_key
CLOUDINARY_API_SECRET=your_cloudinary_api_secret

EMAIL_USERNAME=your_email_username
EMAIL_PASSWORD=your_email_password
EMAIL_HOST=your_email_host
EMAIL_PORT=587
EMAIL_FROM=your_sender_email

FRONTEND_URL=http://localhost:5173

STRIPE_SECRET_KEY=your_stripe_secret_key
STRIPE_API_KEY=your_stripe_publishable_key

GROQ_API_KEY=your_groq_api_key
```

Do not commit `backend/config/config.env`. It contains private credentials.

## Installation

Install backend dependencies:

```bash
cd backend
npm install
```

Install frontend dependencies:

```bash
cd frontend
npm install
```

## Run Locally

Start the backend:

```bash
cd backend
npm start
```

Backend runs on:

```text
http://localhost:4000
```

Start the frontend:

```bash
cd frontend
npm run dev
```

Frontend runs on:

```text
http://localhost:5173
```

## API Base URL

During development, the frontend uses Vite proxy for `/api` requests and sends them to:

```text
http://localhost:4000
```

The proxy is configured in:

```text
frontend/vite.config.js
```

## Useful Commands

Frontend build:

```bash
cd frontend
npm run build
```

Frontend lint:

```bash
cd frontend
npm run lint
```

Backend seed command:

```bash
cd backend
npm run seeder
```

## Deployment Notes

- Set backend environment variables on the hosting platform.
- Set `FRONTEND_URL` to the deployed frontend URL.
- Update backend CORS origin in `backend/app.js` for the deployed frontend.
- Keep MongoDB Atlas network access configured for the deployed backend.
- Never expose Stripe secret key, Cloudinary secret, MongoDB URI, JWT secret, or email password in the frontend.

## License

ISC
