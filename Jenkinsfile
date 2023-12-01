pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                // Comando para construir a aplicação NodeGoat
                sh 'npm install'
            }
        }
        
        stage('Test') {
            steps {
                // Comando para rodar os testes da aplicação
                sh 'npm test'
            }
        }
        
        stage('Docker Build') {
            steps {
                // Comando para construir o projeto nos containers
                sh 'docker build -t teste .'
            }
        }
        
        stage('Docker Run') {
            steps {
                // Comando para rodar o projeto nos containers
                sh 'docker-compose up -d'
            }
        }
    }
    
    post {
        always {
            // Realiza a limpeza após a execução do pipeline, se necessário
            sh 'docker-compose down'
        }
    }
}
