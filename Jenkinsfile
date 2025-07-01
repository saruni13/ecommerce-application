pipeline {
  agent any

  environment {
    MONGO_URI = credentials('mongo-uri') // If using Jenkins credentials store
    RENDER_URL = 'https://your-app.onrender.com' // Replace with your URL
  }

  stages {
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Build & Deploy') {
      steps {
        sh 'node server.js &'
        // Add render deploy script here if any, or manual Render deploy
      }
    }
  }

   post {
    always {
      echo 'Pipeline finished.'
    }
  }
}