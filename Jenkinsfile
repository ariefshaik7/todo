pipeline {
    agent any
    
    stages {
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