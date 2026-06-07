pipeline {
    agent none

    stages {

        stage('Node Environment') {
            agent {
                docker {
                    image 'node:16-alpine'
                }
            }
            steps {
                sh 'node --version'
                sh 'npm --version'
            }
        }

        stage('Run Application') {
            agent {
                docker {
                    image 'node:16-alpine'
                }
            }
            steps {
                sh 'npm install'
                sh 'node app.js'
            }
        }
    }

    post {
        success {
            echo 'Hello Node App executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
