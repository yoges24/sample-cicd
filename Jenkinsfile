pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                sh 'docker build -t node-app .'
                sh 'docker tag node-app:latest yogeshwaran24/sample:v1'
                withCredentials([usernamePassword(credentialsId: 'docker-hub', passwordVariable: 'DOCK_PASS', usernameVariable: 'DOCK_USER')]) {
                    sh "echo $DOCK_PASS | docker login -u $DOCK_USER --password-stdin"
                    sh 'docker push yogeshwaran24/sample:v1'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                sh 'ssh deploy-user@prod-server "docker pull your-username/node-app:latest && docker run -d -p 3000:3000 your-username/node-app:latest"'
            }
        }
    }
}
