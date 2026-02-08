pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                bat 'docker build -t elavarasi-website:latest .'
            }
        }

        stage('Run Docker Container') {
            steps {
                bat '''
                docker stop elavarasi-site
                docker rm elavarasi-site
                docker run -d -p 8081:80 --name elavarasi-site elavarasi-website:latest
                '''
            }
        }
    }
}
