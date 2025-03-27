pipeline {
    agent any
    stages {
        stage('Verify Docker') {
            steps {
                script {
                    sh 'docker --version'
                }
            }
        }
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("yogeshwaran24/sample${BUILD_NUMBER}")
                }
            }
        }
    }
}
