pipeline {
    agent any

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/YOUR-USERNAME/YOUR-REPO.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t devops-website .'
            }
        }

        stage('Run Docker Container') {
            steps {
                sh '''
                docker rm -f devops-container || true
                docker run -d -p 8081:80 --name devops-container devops-website
                '''
            }
        }
    }
}
