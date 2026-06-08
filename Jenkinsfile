pipeline {
    agent any

    stages {

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t flask-devops:v1 .'
            }
        }

        stage('Remove Old Container') {
            steps {
                sh 'docker rm -f flask-app || true'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker run -d -p 5000:5000 --name flask-app flask-devops:v1'
            }
        }
    }
}
