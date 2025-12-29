pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image "node:18-alpine"
                    args '-u root'
                    reuseNode true
                }
            }
            steps {
                sh '''
                    ls -la
                    npm install
                '''
                sh 'npm run build'
            }
        }
    }
}
