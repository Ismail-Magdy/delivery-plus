pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling latest code from GitHub'
                checkout scm
            }
        }
        stage('Install Dependencies') {
            steps {
                echo 'Installing project dependencies'
                sh 'npm ci' 
            }
        }
    }
}