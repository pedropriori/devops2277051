pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                sh 'npm install'
            }
        }
        
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        
        stage('Docker Build') {
            steps {
                sh 'docker build -t teste .'
            }
        }
        
        stage('Docker Run') {
            steps {
                sh 'docker-compose up -d'
            }
        }
    }
    
    post {
        always {
            sh 'docker-compose down'
        }
    }
}
