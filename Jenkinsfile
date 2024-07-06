pipeline {
    agent any

    stages {
        stage('Hello') {
            steps {
               /* def userInput = input(
                        message: 'Please enter your input:',
                        parameters: [string(defaultValue: '', description: 'User input')]
                    )*/
                    
                    // Print user input
                    echo "User input git : $username"
            }
        }

         stage("verify tooling") {
            steps {
            sh '''
                docker version
                docker info
                docker compose version 
                curl --version
                jq --version
             '''
            }
        }
    }
}