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
                    npm install
                    npm run build
                '''
            }
        }
    }
}
