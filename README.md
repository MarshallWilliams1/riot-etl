Riot Games Match Data Analytics Platform
An ETL pipeline and visualization dashboard for League of Legends Challenger tier data.

Description
This project is a full-stack data analytics platform that automatically collects, processes, and visualizes match data for the top players in League of Legends. It was built to practice data engineering principles, including API integration, ETL pipeline design, and data modeling. The application serves the processed insights through a REST API to a responsive React frontend, providing a user-friendly interface for exploring high-level game metadata.

Tech Stack
Backend: Python, Flask

Frontend: React (Vite), JavaScript, Tailwind CSS, React Router

Database: MySQL

Data Fetching: Riot Games API, requests

Libraries: axios, mysql-connector-python

Features
Automated ETL Pipeline: A Python script that fetches data for the top 100 Challenger players, gathers their recent match histories, processes thousands of unique matches, and loads the results into a MySQL database.

RESTful Backend API: A Flask server that exposes endpoints to serve aggregated champion statistics and the live Challenger leaderboard.

Champion Stats Page: Displays the win rate and play count for all champions found in the collected match data.

Live Leaderboard: Shows a real-time, ranked list of the top Challenger players, including their current LP and unique identifiers.

Screenshots
Champion Statistics Page:
A view of the main dashboard displaying champion performance metrics.

Live Challenger Leaderboard:
The leaderboard page showing players ranked by their current LP.

Local Setup
To clone and run this project locally, you will need Node.js, Python, and a local MySQL server installed.

1. Clone the Repository
git clone [https://github.com/your-username/RiotETLAnalytics.git](https://github.com/your-username/RiotETLAnalytics.git)
cd RiotETLAnalytics

2. Backend Setup
Navigate to the backend directory:

cd backend

Create a .env file and add your credentials. This file should be in the backend folder.

RIOT_API_KEY="YOUR_RIOT_API_KEY_HERE"
DB_HOST="localhost"
DB_USER="root"
DB_PASSWORD="your_mysql_password"
DB_DATABASE="lol_analytics"

Install the required Python packages:

pip install -r requirements.txt

3. Database Setup
Ensure your MySQL server is running.

Connect to your MySQL instance and run the script located at database/schema.sql to create the necessary database and tables.

4. Frontend Setup
In a new terminal, navigate to the frontend directory:

cd frontend

Install the required Node.js packages:

npm install

5. Running the Application
The application requires both the backend and frontend servers to be running simultaneously.

Run the Backend (Terminal 1):

# Make sure you are in the 'backend' directory
python -m flask --app api/app run

Run the Frontend (Terminal 2):

# Make sure you are in the 'frontend' directory
npm run dev

Populate the Database:
The first time you run the application, the database will be empty. Go to the "Champion Stats" page and click the "Refresh Latest Match Data" button to run the ETL pipeline. This will take several minutes to complete due to API rate limits.

My Role
This is a solo project. I designed and built the entire application, from the backend data pipeline and API to the frontend user interface.
