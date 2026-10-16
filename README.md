# Air Guard — Air Quality Monitoring & Prediction System

An IoT-based air quality monitoring and prediction platform designed to collect environmental sensor readings, integrate weather information, and provide air quality insights through a connected backend and dashboard.

## Overview

Air Guard brings together IoT data collection, backend services, environmental information, and AI-based prediction in one system. It is designed to help users understand air quality conditions and support awareness of potentially unhealthy pollution levels.

## Key Components

- **IoT data integration:** Retrieves air quality measurements from a connected ThingSpeak channel.
- **Air quality data management:** Stores current and historical readings using PostgreSQL and Prisma ORM.
- **Backend API:** Provides endpoints for device management, sensor readings, weather information, and predictions.
- **Weather data integration:** Retrieves external weather information to complement air quality data.
- **AI prediction integration:** Includes a Python-based AI model component and a backend job for running prediction tasks.
- **Scheduled processing:** Includes jobs for sensor-data synchronisation, weather updates, and AI processing.
- **Admin dashboard:** Includes a dashboard component for viewing and managing system information.

## Technology Stack

| Area | Technologies |
|---|---|
| Backend | Node.js, Express.js, TypeScript |
| Database | PostgreSQL |
| ORM | Prisma |
| AI / Machine Learning | Python |
| IoT data integration | ThingSpeak |
| External data | Weather API integration |
| Frontend | Admin dashboard |
| Scheduled tasks | Node-Cron |

## System Architecture

```text
IoT Sensor Data
      |
      v
ThingSpeak Integration
      |
      v
Node.js / Express Backend
      |
      +------> PostgreSQL Database
      |
      +------> Weather Data Integration
      |
      +------> Python AI Model
      |
      v
Air Quality Data & Predictions
      |
      v
Admin Dashboard
```

*This diagram represents the intended component flow; it does not by itself confirm that every component is currently operating end to end.*

## Data Handled

The backend's sensor-reading integration maps the following fields:

- PM1.0
- PM2.5
- PM10
- Temperature
- Humidity
- AQI
- Wi-Fi signal strength (RSSI)
- PMS sample count

The backend also includes database models for current readings, historical readings, weather forecasts, devices, and predictions.

## Repository Structure

```text
air_guard-_back/
├── src/
│   ├── config/
│   ├── controllers/
│   ├── jobs/
│   ├── routes/
│   ├── services/
│   ├── utils/
│   ├── validators/
│   ├── app.ts
│   ├── prisma.ts
│   └── server.ts
├── prisma/
├── dist/
├── package.json
├── package-lock.json
├── prisma.config.ts
└── tsconfig.json
```

The repository also contains an AI model component and dashboard-related directories. Exact directory contents may vary by branch.

## Getting Started

### Prerequisites

- Node.js and npm
- PostgreSQL
- Python and the dependencies required by the AI model, if running the prediction component
- Access to the external services configured for your environment

### Setup

1. Clone the repository:

   ```bash
   git clone https://github.com/sahan721/air_guard-_back.git
   cd air_guard-_back
   ```

2. Install backend dependencies:

   ```bash
   npm install
   ```

3. Configure the environment variables required by the backend. Use a local `.env` file and keep real credentials out of Git.

4. Configure the PostgreSQL connection and Prisma settings according to the project's existing configuration.

5. Generate the Prisma client if required by the project:

   ```bash
   npx prisma generate
   ```

6. Use the available scripts in `package.json` to build or run the backend.

> **Note:** Exact environment-variable names, database migration steps, Python setup, and run commands depend on the project's configuration. Confirm them in the source files and `package.json` before running the system. The setup instructions above have not been verified as a complete deployment procedure.

## Security

- Keep database credentials and API keys in environment variables.
- Do not commit `.env` files or other secrets.
- Restrict production API access and configure CORS for trusted origins.
- Use appropriate access controls for device management and administrative operations.

## Project Status

This repository contains backend services, database integration, scheduled jobs, an AI prediction integration, and dashboard-related components.

The presence of these components does not guarantee that every feature is fully tested or deployed. End-to-end operation, model accuracy, and production readiness should be confirmed through testing.

## Future Improvements

- Add automated tests for API endpoints and scheduled jobs.
- Document API endpoints with request and response examples.
- Publish measured AI model evaluation results.
- Add verified dashboard screenshots and a live demo, where available.
- Improve deployment configuration and operational monitoring.

## Author

**Sahan Nimnaka**

GitHub: [@sahan721](https://github.com/sahan721)

---

*Air Guard is a software project exploring IoT-based air quality monitoring, environmental data integration, and AI-assisted air quality prediction.*
