pipeline {
    agent any
    environment {
        DOCKER_CREDENTIALS = credentials('dockerhub')
    }
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'sudo docker build -t yogeshwaran24/sample:v1 .'
            }
        }
        stage('Push to Docker Hub') {
            steps {
                sh '''
                echo $DOCKER_CREDENTIALS_PSW | docker login -u yogeshwaran24 --password-stdin
                sudo docker push yogeshwaran24/sample:v1 
                '''
            }
        }
        stage('Run Docker Container') {
            steps {
                sh 'sudo docker run -d -p 80:3000 yogeshwaran24/sample:v1'
            }
        }
    }
}
