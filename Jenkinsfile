pipeline {
    agent any
    
    environment {
        DOCKERHUB_CREDENTIALS = credentials('arief-dockerhub')
        IMAGE_NAME = "ariefshaik007/todo-app"
        IMAGE_TAG = "${BUILD_NUMBER}"
    }
    stages {
        stage('Build'){
            steps {
                sh 'docker build -t $IMAGE_NAME:$IMAGE_TAG .'
            }
        }
        stage('Run container with Docker Compose'){
            steps {
                sh 'IMAGE_TAG=$IMAGE_TAG docker compose up -d --build'
            }
        }
        stage('Stop containers'){
            steps {
                sh 'docker compose down'
            }
        }
        stage('Login'){
            steps {
                sh 'echo $DOCKERHUB_CREDENTIALS_PSW | docker login -u $DOCKERHUB_CREDENTIALS_USR --password-stdin'
            }
        }
        stage('Push'){
            steps {
                sh 'docker push $IMAGE_NAME:$IMAGE_TAG'
            }
        }
        
    }
    post {
        always {
            sh 'docker logout'
        }
        success {
            echo "Pipeline Succeeded"
        }
        failure {
            echo "Pipeline Failed"
        }
    }
}