# EV Charging Demand Forecast Dashboard
This is a React-based conversion of the original Streamlit EV charging dashboard, providing all the core functionality with an improved user experience and a scalable frontend-backend architecture.

Features
Real-time Forecasting: Demand prediction using the Prophet ML model

Overload Analysis: Identifies stations nearing or exceeding capacity

Solar Integration: Highlights stations suitable for solar-powered charging

What-If Simulator: Test scenarios by changing station capacities and demand assumptions

Interactive Maps: Visualizes station locations and insights

Responsive Design: Built with Material-UI for a consistent experience across devices

Prerequisites
Node.js (v14 or higher)

Python 3.8+

npm or yarn

Setup Instructions
Install Python Dependencies

bash
Copy
Edit
cd backend
pip install -r requirements.txt
Install React Dependencies

bash
Copy
Edit
npm install
Start Backend API

bash
Copy
Edit
cd backend
python app.py
The Flask API will run on http://localhost:5000

Start React Frontend

bash
Copy
Edit
npm start
The app will be available at http://localhost:3000

Architecture
Backend (Flask API)
simulate_ev_data.py: Generates synthetic EV charging data

app.py: Flask API with the following endpoints:

/api/stations – Get station list

/api/forecast – Predict demand

/api/overload-analysis – Identify capacity issues

/api/solar-analysis – Find solar-suitable stations

/api/what-if-simulation – Run scenario tests

/api/top-stations – Rank stations by usage

Frontend (React + TypeScript)
EVDashboard: Main dashboard container

StationFilters: Controls for station, vehicle type, and date

ForecastChart: Visualizes demand forecast

OverloadAnalysis, SolarAnalysis, WhatIfSimulator: Display insights and simulations

TopStationsTable: Lists top stations by predicted usage

Key UI Components
Dashboard: Central workspace for all functionality

Filters Panel: Select station, vehicle type, and date

Forecast Chart: 24-hour demand with confidence intervals

Overload/Solar Panels: Highlight infrastructure and energy insights

Station Map: Interactive visualization of station distribution

What-If Simulator: Infrastructure planning tool

Design & User Experience
Built with Material-UI for a consistent, modern look

Fully responsive layout for desktop and mobile

Interactive charts using Recharts

Real-time updates on user input

Robust loading and error states for smooth UX

Customization
Add New Stations: Edit the stations array in simulate_ev_data.py

Change Capacity Limits: Update the station_capacity dictionary in app.py

Update Styling: Modify the theme in src/App.tsx or edit individual components

Deployment
Frontend
bash
Copy
Edit
npm run build
# Deploy the 'build' folder to your hosting provider
Backend
Deploy the Flask app to a cloud service (e.g., Heroku, AWS, Azure)

Data Flow
React frontend sends API requests to Flask backend

Backend simulates data and performs forecasting

Processed data is returned to frontend

Frontend renders data using interactive components
