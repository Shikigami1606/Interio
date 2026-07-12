
# Interio Design Hub

A full-stack interior design platform with React frontend and Express backend.

## Project Structure

```
interio-design-hub-main/
├── frontend/                 # React + Vite frontend application
│   ├── src/                 # Frontend source code
│   ├── public/              # Static assets
│   ├── package.json         # Frontend dependencies
│   ├── vite.config.ts       # Vite configuration
│   ├── tailwind.config.ts   # Tailwind CSS configuration
│   ├── components.json      # shadcn-ui configuration
│   ├── netlify.toml         # Netlify deployment config
│   ├── .env                 # Frontend environment variables (git ignored)
│   ├── .env.example         # Frontend environment template
│   └── supabase/            # Supabase configuration
│
├── backend/                  # Express.js API server
│   ├── src/
│   │   ├── index.js         # Express app entry point
│   │   ├── routes/          # API route handlers
│   │   ├── models/          # MongoDB schemas
│   │   └── middleware/      # Express middleware
│   ├── package.json         # Backend dependencies
│   ├── .env                 # Backend environment variables (git ignored)
│   ├── .env.example         # Backend environment template
│   └── uploads/             # Local file uploads directory
│
├── README.md                # This file
├── .gitignore               # Git ignore patterns
└── package.json             # (Optional) Root workspace configuration
```

## Technology Stack

**Frontend:**
- Vite + React 18 + TypeScript
- shadcn-ui + Tailwind CSS
- React Router + React Query
- Supabase integration
- Cloudinary for image uploads

**Backend:**
- Express.js
- MongoDB with Mongoose
- JWT Authentication
- CORS enabled

## Quick Start

### Prerequisites
- **Node.js** 18+ ([install nvm](https://github.com/nvm-sh/nvm))
- **npm** or **bun**

### Frontend Setup

```bash
cd frontend

# Copy environment template and add your values
cp .env.example .env

# Install dependencies
npm install

# Run development server (Vite)
npm run dev

# Build for production
npm run build
```

Frontend runs on: **http://localhost:5173**

### Backend Setup

```bash
cd backend

# Copy environment template and add your values
cp .env.example .env

# Install dependencies
npm install

# Run development server
npm run dev

# Run production server
npm run start
```

Backend runs on: **http://localhost:4000**

## Environment Variables

### Frontend (`frontend/.env`)
```
VITE_SUPABASE_PROJECT_ID=<your-project-id>
VITE_SUPABASE_PUBLISHABLE_KEY=<your-key>
VITE_SUPABASE_URL=<your-supabase-url>
VITE_API_BASE_URL=http://localhost:4000
```

### Backend (`backend/.env`)
```
MONGODB_URI=<your-mongodb-connection-string>
CLIENT_ORIGINS=http://localhost:5173,http://localhost:8080
PORT=4000
JWT_SECRET=<your-jwt-secret>
UPLOADTHING_SECRET=<your-uploadthing-secret>
UPLOADTHING_APP_ID=<your-uploadthing-app-id>
NODE_ENV=development
```

## API Endpoints

- `GET /api/health` – Health check
- `GET/POST /api/designs` – Design CRUD operations
- `POST /api/auth/login` – User authentication
- `POST /api/auth/register` – User registration

## Scripts

### Frontend
```bash
npm run dev          # Development server
npm run build        # Production build
npm run preview      # Preview production build
npm run lint         # Run ESLint
npm test             # Run tests
npm test:watch       # Watch mode tests
```

### Backend
```bash
npm run dev          # Development server
npm run start        # Production server
```

## Deployment

### Frontend (Netlify)
1. Deploy `frontend/` folder to Netlify
2. Set build command: `npm run build`
3. Set publish directory: `dist`
4. Add environment variables in Netlify dashboard

### Backend (Render.com, Railway, or Heroku)
1. Deploy `backend/` folder to your platform
2. Set build command: `npm install`
3. Set start command: `npm run start`
4. Add environment variables

## Development Tips

- **CORS**: Update `backend/src/index.js` with your frontend URL for production
- **API URL**: Update `VITE_API_BASE_URL` in frontend `.env` when deploying
- **Database**: Ensure MongoDB connection string is valid
- **Secrets**: Never commit `.env` files to git (they're in `.gitignore`)

## Contributing

1. Fork the repository
2. Create a branch for your feature
3. Make your changes
4. Push and create a Pull Request

## License

MIT
