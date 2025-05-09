# dynamic-Flask-web-app-with-a-Redis
Dynamic Web App with Flask, Redis, and Docker on AWS EC2
📌 Project Overview
This project demonstrates deploying a dynamic Flask web application with a Redis backend, containerized using Docker, and hosted on an AWS EC2 instance. The app tracks page hits in real-time, showcasing container orchestration, cloud networking, and development workflows with bind mounts for live updates.
🛠️ Tech Stack

AWS EC2 (Ubuntu 22.04)
Docker & Docker Compose
Flask (Python web framework)
Redis (in-memory data store)
AWS Security Groups (networking)

🚀 Features

A Flask app (app.py) that increments a hit counter using Redis.
A lightweight Dockerfile based on Python 3.7 Alpine.
A docker-compose.yml orchestrating Flask and Redis, mapping port 9000 to 5000.
Bind mounts (./:/app) for live code updates during development.
Deployed on EC2 with public access via AWS security groups.
Tested rebuild (--build) vs. bind mount workflows for dev vs. production.

📂 Project Structure
project/
├── app.py              # Flask application code
├── Dockerfile          # Builds Flask app image
├── requirements.txt    # Python dependencies (Flask, Redis)
├── docker-compose.yml  # Orchestrates Flask + Redis containers
└── README.md           # Project documentation

🔧 How to Run
Prerequisites

AWS account with EC2 instance (Ubuntu)
Docker and Docker Compose installed
Git installed

Steps

Clone the Repository:
git clone <repo-url>
cd project


Start Containers:
docker compose up -d


Access the App:




Test Live Updates (with bind mounts):

Edit app.py (e.g., change the greeting text).
Refresh the browser to see changes without rebuilding.


Stop Containers:
docker compose down



📖 Key Learnings

Docker Fundamentals: Built and managed containers with Dockerfile and Docker Compose.
Container Networking: Configured port mappings and service communication (Flask ↔ Redis).
AWS Networking: Debugged EC2 security groups and public IP access.
Development Workflows: Used bind mounts for live code updates, contrasting with image rebuilds.
Production Insights: Understood trade-offs between dev flexibility and production stability.

🔍 Troubleshooting

Browser Spinning: Ensure EC2 security group allows inbound TCP on port 9000 from 0.0.0.0/0.
Redis Connection Errors: Verify redis service is running (docker ps) and host='redis' in app.py.
Changes Not Reflecting: Confirm bind mount (./:/app) is in docker-compose.yml or rebuild with docker compose up -d --build.

🔗 Live Demo
If deployed on EC2, 
📈 Next Steps

Add Nginx as a reverse proxy for production-grade routing.
Implement CI/CD with GitHub Actions for automated deployments.
Explore AWS ECS for container orchestration at scale.

💡 Why This Matters
This project simulates real-world DevOps tasks: deploying a multi-container app, managing cloud networking, and optimizing development workflows. It’s a stepping stone to production-grade systems and automation pipelines.
