pipeline {
    agent any
    // environment {
    //     DOCKER_CREDENTIALS = credentials('dockerhub') // Use stored Docker credentials securely
    // }
    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker.build("yogeshwaran24/sample"+"$BUILD_NUMBER")'
            }
        }
        // stage('Push to Docker Hub') {
        //     steps {
        //         sh '''
        //         echo $DOCKER_CREDENTIALS_PSW | docker login -u $DOCKER_CREDENTIALS_USR --password-stdin
        //         docker push yogeshwaran24/sample:v1
        //         '''
        //     }
        // }
        // stage('Run Docker Container') {
        //     steps {
        //         sh 'docker run -d -p 80:3000 yogeshwaran24/sample:v1'
        //     }
        // }
    }
}
