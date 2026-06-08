pipeline {
agent any


environment {
    IMAGE_NAME = "girjesh111/flask-devops:v1"
}

stages {

    stage('Build Docker Image') {
        steps {
            sh 'docker build -t $IMAGE_NAME .'
        }
    }

    stage('Push Docker Image') {
        steps {
            sh 'docker push $IMAGE_NAME'
        }
    }

    stage('Deploy To Kubernetes') {
        steps {
            sh 'kubectl apply -f k8s/'
        }
    }

    stage('Verify Deployment') {
        steps {
            sh 'kubectl get pods'
            sh 'kubectl get svc'
        }
    }
}


}
