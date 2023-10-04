pipeline {
    agent any
    tools {
        nodejs 'Node18'
    }
    stages {
        stage('Checkout') {
            steps {
                checkout scm 
                echo 'Checked out!'
            }
        }
        stage('Build and Dockerize') {
            steps {
                sh 'npm install' 
                sh 'npm run build' 
                sh 'docker build -t vite-img .' 
                sh 'docker run -p 3000:3000 vite-img' 
        }
    }
}
}
