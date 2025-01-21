pipeline {
    agent any

    stages {
        stage('Build') {
            agent{
                docker{
                    image 'node:20-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Building..'
                sh '''
                    npm --version
                    npm ci
                    npm build
                    ls -l
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