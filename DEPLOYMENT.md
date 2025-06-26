# Deployment Guide

## Backend Deployment (Render)

### Method 1: Using Render Dashboard (Recommended)

1. Go to https://render.com and sign up/login
2. Click "New +" → "Web Service"
3. Connect your GitHub repository
4. Select the backend folder
5. Configure:
   - **Build Command**: `npm install`
   - **Start Command**: `npm start`
   - **Environment**: Node

### Environment Variables to Set in Render Dashboard:

```
NODE_ENV=production
PORT=4000
DB_URL=<your_mongodb_atlas_connection_string>
CLOUDINARY_API_KEY=<your_cloudinary_api_key>
CLOUDINARY_API_SECRET=<your_cloudinary_api_secret>
CLOUDINARY_CLOUD_NAME=<your_cloudinary_cloud_name>
JWT_SECRET_KEY=<generate_a_secure_random_string>
JWT_EXPIRE=7d
COOKIE_EXPIRE=7
FRONTEND_URL=https://your-frontend-app.vercel.app
```

## Frontend Deployment (Vercel)

1. Go to https://vercel.com and sign up/login
2. Import your GitHub repository
3. Select the frontend folder
4. Configure:
   - **Framework Preset**: Vite
   - **Build Command**: `npm run build`
   - **Output Directory**: `dist`

### Environment Variables to Set in Vercel:

```
VITE_API_URL=https://your-backend-app.onrender.com
```

## Deployment Order:

1. Deploy Backend first (get the URL)
2. Update FRONTEND_URL in backend env vars
3. Update VITE_API_URL with backend URL
4. Deploy Frontend

## Alternative Platforms:

### Backend Options:
- Railway
- Heroku
- DigitalOcean App Platform
- AWS Elastic Beanstalk

### Frontend Options:
- Netlify
- GitHub Pages
- Firebase Hosting
- Surge.sh
