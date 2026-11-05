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
    }
}