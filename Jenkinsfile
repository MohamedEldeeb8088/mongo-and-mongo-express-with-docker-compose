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
                sh 'docker compose up -d'
                sh 'docker compose ps'
            }
            post {
                failure {
                sh 'docker compose down --remove-orphans -v'
                sh 'docker compose ps'
                sh 'docker compose up -d' 
                }
                success {
                    echo"success2"
                }

                
                
            }
        }
    }
    
}