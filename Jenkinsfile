pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/YOUR-USERNAME/nodeapp.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t nodeapp:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh '''
                docker stop nodeapp || true
                docker rm nodeapp || true
                docker run -d -p 3000:3000 --name nodeapp nodeapp:latest
                '''
            }
        }
    }
}
