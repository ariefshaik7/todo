pipeline {
    agent any
    
    stages {
        stage('Cloning the repository') {
            steps {
                git credentialsId: 'github-token', url: 'https://github.com/ariefshaik114/todo.git'
            }
        }
        stage('Build and run application using Docker Compose'){
            steps {
                sh 'docker compose up -d'
            }
        }
        
    }
    post {
        always {
            echo "Cleaning up containers..."
            sh 'docker compose down'
        }
    }
}