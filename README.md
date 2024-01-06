
# MP3 Converter Microservices

This project is a FastAPI implementation of a video to mp3 converter system.

## Components

### Api-Gateway
- Gateway handling incoming requests from clients.
- Stores uploaded videos in a MongoDB database.
- Sends a message to RabbitMQ when a video is uploaded.

### Users-Service
- Handles user registration and authentication.
- Stores user data in a MySQL database.

### Converter-Service
- Consumes messages from RabbitMQ to download and convert videos to mp3.
- Stores the mp3 files in MongoDB.
- Sends a message to RabbitMQ with the mp3 file ID.

### Notification-Service
- Consumes messages from RabbitMQ to get mp3 file ID.
- Sends an email to the client with the mp3 file ID.

## Running with Docker Compose

### Run Docker Compose
```bash
docker-compose up
# Or run in detached mode
docker-compose up -d
```
