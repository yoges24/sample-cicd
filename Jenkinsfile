pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("yogeshwaran24/sample${BUILD_NUMBER}")
                }
            }
        }
    }
}
