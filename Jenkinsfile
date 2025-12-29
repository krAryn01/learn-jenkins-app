pipeline {
    agent none

    stages {
        stage('Clear WS') {
            steps {
                clearWs()
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
