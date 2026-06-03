pipeline {
agent any

		
stages {

    stage('Pull Public Image') {
        steps {
            sh 'docker pull nginx:latest'
        }
    }

    stage('Deploy To Kubernetes') {
        steps {
            sh '''
            kubectl apply -f deployment.yaml
            kubectl apply -f service.yaml
            '''
        }
    }

    stage('Verify') {
        steps {
            sh '''
            kubectl get pods
            kubectl get svc
            '''
        }
    }
}


}

