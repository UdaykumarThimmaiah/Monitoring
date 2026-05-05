# Monitoring Project

## Project Vision
The Monitoring project aims to provide a comprehensive solution for real-time monitoring and analytics, allowing users to efficiently track performance metrics and system health across various applications.

## Key Features
- **Real-Time Monitoring**: Capture and display metrics in real-time for immediate insights.
- **Custom Dashboards**: Users can create personalized dashboards tailored to their specific needs.
- **Alerting Mechanism**: Set up alerts based on predefined thresholds to stay informed of critical issues.
- **Historical Data Analysis**: Access and analyze historical data trends for informed decision-making.
- **Integration Capabilities**: Seamless integration with existing tools and services to enhance functionality.

## Structural Overview
- **Frontend**: Built with React for a responsive user experience.
- **Backend**: Node.js and Express for handling API requests and processing data.
- **Database**: MongoDB for flexible data storage and retrieval.
- **Monitoring Agents**: Lightweight agents for collecting metrics from various sources.

This project is designed to be modular, allowing easy updates and feature additions as the needs evolve.

## Deployment

### Docker Compose (Local / Self-Hosted)

Run the entire stack (frontend, backend, and MongoDB) with a single command:

```bash
docker-compose up --build
```

- Frontend: http://localhost:3000
- Backend API: http://localhost:8000
- MongoDB: localhost:27017

### Backend on Render

1. Go to [render.com](https://render.com) and sign in with GitHub.
2. Click **New → Blueprint** and connect your repository.
3. Render will auto-detect `render.yaml` and create the backend web service.
4. In the service's **Environment** settings, replace the `MONGODB_URI` placeholder with your MongoDB Atlas connection string.

### Frontend on Vercel

1. Go to [vercel.com](https://vercel.com) and click **Import Project**.
2. Select this repository.
3. Set the **Root Directory** to `frontend/`.
4. Vercel will auto-detect the React app and deploy it. The `vercel.json` handles SPA routing automatically.

### MongoDB Atlas (Free Tier)

1. Create a free account at [mongodb.com/atlas](https://www.mongodb.com/atlas).
2. Create a new **free (M0) cluster**.
3. Under **Database Access**, create a database user with a password.
4. Under **Network Access**, add your host's specific IP address. Only allow connections from anywhere (`0.0.0.0/0`) as a temporary measure for development; restrict access to known IPs in production.
5. Click **Connect → Drivers** and copy the connection string.
6. Set the connection string as the `MONGODB_URI` environment variable in your backend host (Render or Docker Compose).