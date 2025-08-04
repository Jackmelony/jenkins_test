pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
               git 'https://github.com/jackmelony/jenkins_test.git'
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
