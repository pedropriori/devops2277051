pipeline {
    agent any

    stages {
    	stage('Test') {
				steps {
					sh '''

						docker build
						docker compose up
                        npm install
                        npm test
						
					'''
				}
    	}
    }
}