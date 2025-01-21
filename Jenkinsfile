pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:20-alpine'
                }
            }
            steps {
                echo 'Building..'
                sh '''
                    npm --version
                '''
            }
        }
        stage('Test') {
            steps {
                echo 'Testing pipeline auto trigger..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}