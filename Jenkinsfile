pipeline {
    agent none

    stages {
        
        stage('Build') {
            agent {
                docker {
                    image "node:18-alpine"
                    reuseNode true
                }
            }
            steps {
                clearWs()
                sh '''
                    ls -la
                    npm install
                    npm run build
                '''
            }
        }
    }

}
