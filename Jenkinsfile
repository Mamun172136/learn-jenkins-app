pipeline {
    agent any

    stages {
        stage('Build') {
            agent {
                docker {
                    image 'node:18-alpine'
                    reuseNode true
                    args '-v C:/Users/hp/.jenkins/workspace/learn-app:/workspace -w /workspace' // Corrected volume and working directory
                }
            }
            steps {
                bat '''
                    echo "Listing workspace files:"
                    dir /s
                    node --version
                    npm --version
                    npm ci
                    npm run build
                '''
            }
        }
        stage("Test") {
            steps {
                echo 'Test stage'
            }
        }
    }
}
