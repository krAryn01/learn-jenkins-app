pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image "node:18"
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    whoami
                    npm ci
                    npm run build
                '''
            }
        }
        stage('Test') {
            agent {
                docker {
                    image "node:18"
                    reuseNode true
                }
            }
            steps {
                sh 'npm test'
            }
        }
    }
    post {
        failure {
            cleanWs()
        }
    }
}
