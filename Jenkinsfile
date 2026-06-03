pipeline {
agent any

```
stages {

    stage('Pull Public Docker Image') {
        steps {
            sh '''
            docker pull nginx:latest
            docker images | grep nginx
            '''
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

    stage('Verify Deployment') {
        steps {
            sh '''
            kubectl get pods -o wide
            kubectl get svc
            '''
        }
    }
}
```

}

