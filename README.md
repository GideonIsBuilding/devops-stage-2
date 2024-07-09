# Full-Stack FastAPI and React Template

Welcome to the Full-Stack FastAPI and React template repository. This repository serves as a demo application for interns, showcasing how to set up and run a full-stack application with a FastAPI backend and a ReactJS frontend using ChakraUI.

## Project Structure

The repository is organized into two main directories:

- **frontend**: Contains the ReactJS application.
- **backend**: Contains the FastAPI application and PostgreSQL database integration.

Each directory has its own README file with detailed instructions specific to that part of the application.

## Getting Started

To get started with this template, please follow the instructions in the respective directories:

- [Frontend README](./frontend/README.md)
- [Backend README](./backend/README.md)

# Full Deployment Guide

This guide provides instructions for deploying our full-stack application (React frontend, FastAPI backend, and PostgreSQL database) both manually and using Docker.

## Table of Contents

1. [Manual Deployment](#manual-deployment)
2. [Docker Deployment](#docker-deployment)

## Manual Deployment

For manual deployment, read the `Readme.md` files in the [Frontend](./frontend/README.md) and [Backend](./backend/README.md) directories.

## Docker Deployment

### Prerequisites

- Docker - [How To Install](https://medium.com/@srijaanaparthy/step-by-step-guide-to-install-docker-on-ubuntu-in-aws-a39746e5a63d)
- Docker Compose - [How To Install](https://aqibhafeez473.hashnode.dev/day-13-setting-up-docker-compose-on-aws-ec2-instance-with-ubuntu#heading-step-4-install-docker-compose)

### Steps

1. Clone the repository:
   `git clone https://github.com/GideonIsBuilding/devops-stage-2.git`
2. Then change directories `cd devops-stage-2`
3. Create a `.env` file in the root directory and add necessary environment variables.
4. Build and start the containers: `docker-compose up -d --build`
5. Run database migrations: `docker-compose exec backend alembic upgrade head`
6. The application should now be running. You will find five processes running when you run the `docker-compose ps` like this:

![Image](".Screenshot/image.png")

7. Enter the following URLs in your browser to be extra sure:

- Frontend: http://localhost:5174
- Backend API: http://localhost:8000
- Adminer (Database Management): http://localhost:8080

### Additional Configuration

- Nginx Proxy Manager is available at http://localhost:8090
- Default login:
  Email: admin@example.com
  Password: changeme
- Configure proxy hosts for your domain

### Stopping the Application

docker-compose down

## Accessing the Application

- Frontend: http://yourdomain.com
- Backend API: http://yourdomain.com/api
- API Documentation: http://yourdomain.com/docs
- Adminer: http://db.yourdomain.com
- Nginx Proxy Manager: http://proxy.yourdomain.com

## Troubleshooting

- Check Docker logs: `docker-compose logs [service_name]`
- Ensure all required ports are open in your firewall
- Verify DNS settings if using a custom domain

## Security Considerations

- Change default passwords
- Use HTTPS for all services in production
- Regularly update dependencies and Docker images

For more detailed information or troubleshooting, please refer to the individual README files in the frontend and backend directories.
