pipeline {
    agent {
        docker {
            image 'docker:latest'
            args '-v /var/run/docker.sock:/var/run/docker.sock'
        }
    }
    environment {
        DOCKER_CREDENTIALS = credentials('dockerhub') // Use stored Docker credentials securely
    }
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t yogeshwaran24/sample:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                sh '''
                echo $DOCKER_CREDENTIALS_PSW | docker login -u $DOCKER_CREDENTIALS_USR --password-stdin
                docker push yogeshwaran24/sample:v1
                '''
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'docker run -d -p 80:3000 yogeshwaran24/sample:v1'
            }
        }
    }
}
