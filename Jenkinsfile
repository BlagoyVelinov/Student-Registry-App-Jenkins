pipeline {
    agent any
    stages {
        stage('NPM install') {
            steps {
                bat 'npm install'
            }
        }
        stage('Run npm audit tests') {
            steps {
                bat 'npm audit'
            }
        }
        stage('Run integration tests') {
            steps {
                bat 'npm run test'
            }
        }
        stage('Approval for production Deployment') {
            steps {
                script {
                    input message: 'Proceed with production deployment?', ok: 'Deploy'
                }
            }
        }
    }
}
