pipeline {
    agent any
    stages {
        stage('Checkout the Git repository') {
            steps {
                git branch: 'main', url: 'https://github.com/i-am-vibin-antony/docker.git'
            }
        }
        stage('Build Docker image') {
            steps {
                script {
                    def dockerfile = 'Dockerfile'
                    def registry = 'localhost:5000'
                    def imageName = 'hello-world-image'
                    def imageTag = '1.0'
                    def dockerImage = docker.build("${registry}/${imageName}:${imageTag}", "-f ${dockerfile} .")
                    dockerImage.push()
                }
            }
        }
    }
}
