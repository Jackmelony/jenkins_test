pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                git 'https://github.com/YOUR_USERNAME/YOUR_REPO.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    def imageTag = "hello-world-image:${env.BUILD_NUMBER}"
                    sh "docker build -t ${imageTag} ."
                }
            }
        }
    }

    post {
        success {
            echo '✅ Docker image built successfully.'
        }
        failure {
            echo '❌ Docker image build failed.'
        }
    }
}
