pipeline {
    agent any

    environment {
        NETLIFY_SITE_ID = 'a241e30f-31b8-4735-899c-a3237be173df'
        NETLIFY_AUTH_TOKEN = credential('netlify-token')
    }

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
            // agent{
            //     docker{
            //         image 'node:20-alpine'
            //         reuseNode true
            //     }
            // }
            steps {
                echo 'Testing..'
                sh '''
                    npm run test
                '''
            }
        }
        stage('Deploy') {
            // agent{
            //     docker{
            //         image 'node:20-alpine'
            //         reuseNode true
            //     }
            // }
            steps {
                echo 'Deploying..'
                sh '''
                    npm install netlify-cli --save-dev

                '''
                // node_modules/netlify-cli/bin/run.js deploy --dir=build --prod
            }
        }
    }
}