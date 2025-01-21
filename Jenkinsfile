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
                    npm run build
                    ls -l
                '''
            }
        }
        stage('Test') {
            agent{
                docker{
                    image 'node:20-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Testing..'
                sh '''
                    npm run test
                '''
            }
        }
        stage('Deploy') {
            agent{
                docker{
                    image 'node:20-alpine'
                    reuseNode true
                }
            }
            steps {
                echo 'Deploying....'
            }
        }
    }
}