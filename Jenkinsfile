pipeline {
    agent any

    stages {
        stage('Clear WS') {
            steps {
                cleanWs()
            }
        }
        
        stage('Build') {
            agent {
                docker {
                    image "node:18-alpine"
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    npm install
                    npm run build
                '''
            }
        }
    }

}
