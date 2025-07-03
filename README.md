# Overview
This project involved the containerization and deployment of a full-stack yolo application using Docker.


# Requirements
Install the docker engine here:
- [Docker](https://docs.docker.com/engine/install/) 

## How to launch the application 
### Method 1 (faster)
- NOTE: This method does not require cloning of this repository

- Navigate to the launch_app folder and copy the contents of the [docker-compose.yaml] in the root of the project
- On your local machine, navigate to your desired directory and create
  a docker-compose.yaml file, paste the contents into it and save

  
  touch docker-compose.yaml
  

- Launch the application using docker compose up

  
  docker-compose up
  
- Terminate the application using docker compose down
  
    docker-compose down
  ### Method 2
- NOTE: This requires cloning of this whole repository

- Clone this repository to your local machine

  
  git clone https://github.com/bryanphilips/yolo.git
  

- Navigate to the root directory of your cloned repository

  cd yolo

- Launch the application using the docker-compose command

  
  docker-compose up
  

## Access the application on your browser using the following URL
 http://localhost:3000/
#### Screenshot of the launched application
![Yolo frontend](https://github.com/user-attachments/assets/88a04f67-84b9-4018-a436-96cc9bb5348c)

#### Screenshot after adding products
![yolo product persistent](https://github.com/user-attachments/assets/3113fc67-0c62-4195-b40b-94c1d87a8d66)