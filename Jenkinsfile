pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
                echo "User input git : $username"
            }
        }

         stage('Start container') {
            steps {
                sh 'docker compose up -d --no-color --wait'
                sh 'docker compose ps'
            }
        }
        
    }
}