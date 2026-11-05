pipeline {
    agent any
    
    stages {
        stage('Checkout Code') {
            steps {
                echo 'Pulling code from GitHub'
                checkout scm
            }
        }
        stage('Test Pipeline') {
            steps {
                echo 'Hello from Jenkins! The code is ready'
                sh 'ls -la' 
            }
        }
    }
}