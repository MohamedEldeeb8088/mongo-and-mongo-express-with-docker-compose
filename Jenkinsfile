pipeline {
    agent any

    stages {
        stages {
                stage('Check and Start Docker Container ') {
                steps {

                    sh '''#!/bin/bash

                                # Check if the container is running
                                cd ${/home/mohamed1/Desktop/Jenkins}
                                if [ "$(docker ps --filter "name=${mongo-db-services1}" --filter "status=running" -q)" ]; then
                                    echo "Express container is already running."
                                else
                                    echo "Express container is not running. Starting it up..."
                                    docker compose -f ${docker-compose.yml} up -d
                                fi'''

                    echo 'Build Completed'
                    }
            }
        }
        stage('check') {
            steps {
                sh 'docker ps'
                sh 'docker compose ps'
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