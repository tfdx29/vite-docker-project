pipeline {
    agent {
        docker {
            image 'node:16'
        }
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm 
            }
        }
        stage('Build and Dockerize') {
            steps {
                sh 'npm install' 
                sh 'npm run build' 
                sh 'docker build -t vite-img .' 
                sh 'docker run -p 3000:3000 vite-img --name vite-app' 
        }
    }
}
