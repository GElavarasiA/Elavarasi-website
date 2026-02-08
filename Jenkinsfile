pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("elavarasi-website:latest")
                }
            }
        }

        stage('Run Docker Container') {
            steps {
                script {
                    sh '''
                    docker stop elavarasi-site || true
                    docker rm elavarasi-site || true
                    docker run -d -p 8081:80 --name elavarasi-site elavarasi-website:latest
                    '''
                }
            }
        }
    }
}
