# Connecting Two Docker Containers - API and MyBlog(Frontend)
This repository contains two Docker containers that are connected to each other. One of the containers runs an API, while the other runs a frontend for a blog website.

## API Container
The API container is a Node.js application that exposes several endpoints for managing blog posts. It runs on port 4000 and is built using the official node:17-alpine Docker image.

# Build and Run the API Container
To build and run the API container, follow these steps:

1. Clone this repository and navigate to the `api` directory.
2. Run the following command to build the API container:
```
docker build -t api .
```
3. Once the build is complete, run the container using the following command:
```
docker run -d --name api -p 4000:4000 api
```
## MyBlog Container
The MyBlog container is a React application that serves as the frontend for the blog website. It runs on port 3000 and is built using the official node:17-alpine Docker image. The application communicates with the API container to fetch and display blog posts.

## Build and Run the MyBlog Container
To build and run the MyBlog container, follow these steps:

1. Clone this repository and navigate to the `myblog` directory.
2. Run the following command to build the MyBlog container:

```
docker build -t myblog .
```
3. Once the build is complete, run the container using the following command:

```
docker run -d --name myblog -p 3000:3000 myblog
```

## Connecting the Containers
The API container and the MyBlog container are connected to each other through a Docker network. When the containers are started, they are automatically attached to the same network. The MyBlog application communicates with the API using the URL `http://api:4000`.

## Using Docker Compose
Alternatively, you can use Docker Compose to build and run the containers. Docker Compose is a tool for defining and running multi-container Docker applications.

To use Docker Compose, follow these steps:

1. Install Docker Compose on your system. You can download it from the Docker website.
2. Navigate to the root directory of this repository.
3. Run the following command to start the containers:
```
docker-compose up
```
This will build the containers (if necessary) and start them. You should see the output from both containers in your terminal.
4. Once the containers are up and running, you can access the blog website by opening a web browser and navigating to `http://localhost:3000`. You should see the homepage of the blog website, which displays a list of blog posts fetched from the API.
To stop the containers, press `Ctrl+C` in your terminal or run the following command:
```
docker-compose down
```

