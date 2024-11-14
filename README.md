# Project Setup Working Document 

## Project Overview
This project aims to develop an e-commerce website builder with blogging functionality for small businesses. It leverages React for the front-end and Django for the back-end, with payment integration using Stripe.

## Architecture
1. **Presentation Layer (Front-End)**: React app (hosted on Azure Static).
2. **Business Logic Layer (Back-End)**: NopCommerce & .NET Core hosted on Azure Functions.
3. **Data Layer**: MS SQL 
4. **Static Assets**: Azure Blob Storage.
5. **Content Delivery**: Azure CDN.
6. **Content Management**: Strapi hosted on Azure App Service.

## Setup Instructions
### Front-End (React)
1. **Dockerfile**:
    ```dockerfile
    # Use an official Node.js runtime as a parent image
    FROM node:14

    # Set the working directory in the container
    WORKDIR /usr/src/app

    # Copy package.json and install dependencies
    COPY package.json ./
    RUN npm install

    # Copy the rest of the application code
    COPY . .

    # Expose the port the app runs on
    EXPOSE 3000

    # Define the command to run the app
    CMD [ "npm", "start" ]
    ```
2. **Deployment**:
    - Host on Azure Static Web Apps.

### Back-End (Django)
1. **Dockerfile**:
    ```dockerfile
    # Use an official Python runtime as a parent image
    FROM python:3.8

    # Set the working directory in the container
    WORKDIR /usr/src/app

    # Copy the requirements file and install dependencies
    COPY requirements.txt ./
    RUN pip install -r requirements.txt

    # Copy the rest of the application code
    COPY . .

    # Expose the port the app runs on
    EXPOSE 8000

    # Define the command to run the app
    CMD [ "python", "manage.py", "runserver", "0.0.0.0:8000" ]
    ```
2. **Deployment**:
    - Host on Azure Functions.

### Content Management (Strapi)
1. **Dockerfile**:
    ```dockerfile
    # Use an official Node.js runtime as a parent image
    FROM node:14

    # Set the working directory in the container
    WORKDIR /usr/src/api

    # Copy package.json and install dependencies
    COPY package.json ./
    RUN npm install

    # Copy the rest of the application code
    COPY . .

    # Expose the port the app runs on
    EXPOSE 1337

    # Define the command to run the app
    CMD [ "npm", "start" ]
    ```
2. **Deployment**:
    - Host on Azure App Service.

### Database (Azure Cosmos DB)
- Use the free tier to store product details, user data, and blog content.

### Static Files (Azure Blob Storage)
- Store static files such as images.

### Payment Integration (Stripe)
- Install Stripe SDK in Django.
- Securely store Stripe API keys in environment variables.
- Implement payment endpoints in Django.

## Cost Estimates
- **Azure Static Web Apps**: Free tier
- **Azure Functions**: Free tier
- **Azure Cosmos DB**: Free tier
- **Azure Blob Storage**: Free tier
- **Azure App Service**: Free tier

Total estimated monthly cost: **$0 - $20**

## Useful Links
- [Azure Pricing Calculator](https://azure.microsoft.com/en-us/pricing/calculator/)
- [Docker Documentation](https://docs.docker.com/)
- [Stripe API Reference](https://stripe.com/docs/api)
- [Strapi Documentation](https://strapi.io/documentation/)
