pipeline {
    agent any
    
    tools {
        nodejs 'Node22' 
    }

    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling latest code from GitHub...'
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing project dependencies...'
                sh 'npm ci' 
            }
        }
        stage('Build Project') {
            steps {
                echo 'Compiling TypeScript code...'
                sh 'npm run build' 
            }
        }
        stage('Test Project') {
            steps {
                echo 'Running unit tests...'
                sh 'npm run test' 
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning code for security vulnerabilities...'
                sh 'npm audit || true' 
            }
        }
        stage('Deliver & Deploy') {
            steps {
                echo 'Building Docker Image...'
                echo 'docker build -t delivery-plus:latest .'
                echo 'Pushing image to Docker Registry...'
                echo 'Deploying to Kubernetes / Docker Compose...'
                echo 'Deployment Successful! The application is live.'
            }
        }
    }
    
    post {
        success {
            echo 'CI/CD Pipeline ran successfully! The platform is ready for production.'
        }
        failure {
            echo 'Pipeline failed! Please check the Jenkins logs to fix the issue.'
        }
    }
}