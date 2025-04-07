# CSC3916 Assignment 3 API

## Project Overview

This project is a Node.js Web API that uses MongoDB (via Mongoose) to store data for movies, users, and reviews. It provides endpoints to perform CRUD operations on movies and reviews, and implements JWT authentication to secure protected routes. A React-based frontend interacts with this API, and both the API and frontend are deployed on Render.

## Features

- **User Authentication:**  
  Users can sign up and sign in. Passwords are securely hashed using bcrypt, and JWT tokens are issued upon successful authentication.
  
- **Movies CRUD Operations:**  
  Create, read, update, and delete movies with details like title, release date, genre, and actors.
  
- **Reviews CRUD Operations:**  
  Create and read reviews for movies. Reviews include the review text, a rating (0 to 5 stars), and the reviewer's username. Deletion of reviews is also supported.
  
- **Aggregation:**  
  The API supports aggregation for movies, joining related reviews via MongoDB's `$lookup` operator and calculating the average rating.
  
- **Environment-based Configuration:**  
  The API uses environment variables for sensitive data and deployment configuration.

## Installation

1. **Clone the Repository:**    
   git clone https://github.com/maihnguyen/CSCI3916_Assignment4_NguyenM.git

2. Install Dependencies:
    npm install

3. Set up environment variables
    create an .env file in the root directory and add the following variables:
    DB=mongodb+srv://<username>:<password>@cluster0.mongodb.net/yourDatabaseName?retryWrites=true&w=majority
    JWT_SECRET=yourjwtsecretkey
    PORT=3000

    Replace <username>, <password>, and yourDatabaseName with your actual MongoDB Atlas credentials and database name.
    Replace the JWT_SECRET with your jwt key

## Usage
Starting the API:

Start the server with:
    npm start

The API will run on http://localhost:3000 or the port defined in your .env file.

Postman Test collection:
[<img src="https://run.pstmn.io/button.svg" alt="Run In Postman" style="width: 128px; height: 32px;">](https://app.getpostman.com/run-collection/41343022-40af80d6-b79a-4867-a9de-3c0accf90bf0?action=collection%2Ffork&source=rip_markdown&collection-url=entityId%3D41343022-40af80d6-b79a-4867-a9de-3c0accf90bf0%26entityType%3Dcollection%26workspaceId%3Dad6054ea-118a-4d61-818a-5dd1b4f50a13#?env%5BNguyen_HW-4%5D=W3sia2V5IjoicmFuZG9tSWQiLCJ2YWx1ZSI6IjEyNjczNTY3MTI3MzYzIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6IjQyMzEiLCJjb21wbGV0ZVNlc3Npb25WYWx1ZSI6NDIzMSwic2Vzc2lvbkluZGV4IjowfSx7ImtleSI6IkpXVCIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6IkpXVC4uLiIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiSldUIGV5SmhiR2NpT2lKSVV6STFOaUlzSW5SNWNDSTZJa3BYVkNKOS5leUpwWkNJNklqWTNaRGMyWWpBd09XTXdaVGMzWVRrME5tWTNOalZoWmlJc0luVnpaWEp1WVcxbElqb2lZM1ZrWlc1MlpYSjFjMlZ5SWl3aWFXRjBJam94TnpRME1ERXhNems1TENKbGVIQWlPakUzTkRRd01UUTVPVGw5Lll5RHd1TUJZTUxYSlFmY0lhRTkxQkM2M3R0TVRFTmNsMUJXcmdQdklQLUkiLCJzZXNzaW9uSW5kZXgiOjF9LHsia2V5IjoibW92aWVJZCIsInZhbHVlIjoiIiwiZW5hYmxlZCI6dHJ1ZSwidHlwZSI6ImFueSIsInNlc3Npb25WYWx1ZSI6IjY3ZjM4MDg4YTk3MTg0NWMyYzFiMTU0ZSIsImNvbXBsZXRlU2Vzc2lvblZhbHVlIjoiNjdmMzgwODhhOTcxODQ1YzJjMWIxNTRlIiwic2Vzc2lvbkluZGV4IjoyfSx7ImtleSI6InJldmlldzEiLCJ2YWx1ZSI6IiIsImVuYWJsZWQiOnRydWUsInR5cGUiOiJhbnkiLCJzZXNzaW9uVmFsdWUiOiI2N2YzODA0OWE5NzE4NDVjMmMxYjE0ZmYiLCJjb21wbGV0ZVNlc3Npb25WYWx1ZSI6IjY3ZjM4MDQ5YTk3MTg0NWMyYzFiMTRmZiIsInNlc3Npb25JbmRleCI6M30seyJrZXkiOiJyZXZpZXcyIiwidmFsdWUiOiIiLCJlbmFibGVkIjp0cnVlLCJ0eXBlIjoiYW55Iiwic2Vzc2lvblZhbHVlIjoiNjdmMzgwNWJhOTcxODQ1YzJjMWIxNTI3IiwiY29tcGxldGVTZXNzaW9uVmFsdWUiOiI2N2YzODA1YmE5NzE4NDVjMmMxYjE1MjciLCJzZXNzaW9uSW5kZXgiOjR9XQ==)