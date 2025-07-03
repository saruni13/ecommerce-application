E-Commerce Dashboard Application

This repository contains a Dockerized e-commerce application that has been deployed on a Amazon web services (AWS) cluster. The application includes a frontend built with React, a backend using Node.js, and MongoDB as the database.

Setup Instructions
Clone the Repository
git clone git@github.com:saruni13/ecommerce-application.git cd DevOps-Microservice-Setup

start the Vagrant Machine
vagrant up

SSH into the Vagrant Machine
vagrant ssh

Navigate to the Project Directory and Run the Ansible Playbook
ansible-playbook playbook.yml -i hosts

Navigate to the Client Folder
cd client

Run the folllowing command to install the dependencies
npm install

Node version
The client uses an older version of Node, v14, after installing your dependencies, make the following changes to your package.json
"scripts": { "start": "NODE_OPTIONS=--openssl-legacy-provider react-scripts start", "build": "NODE_OPTIONS=--openssl-legacy-provider react-scripts build", "test": "react-scripts test", "eject": "react-scripts eject" },

Run the folllowing to start the app
npm start

Open a new terminal and run the same commands in the backend folder
cd ../backend

npm install

npm start

Steps to Run with Docker
Build the Docker images: docker-compose build
Start the Docker containers: docker-compose up




