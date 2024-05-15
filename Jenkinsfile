
// minikube start --driver=docker --profile=store

pipeline {
    agent any
    stages {
        stage('Deploy on k8s') {
            steps {
                withCredentials([ string(credentialsId: 'minikube-credentials', variable: 'token') ]) {
                    sh 'kubectl --token $token --server https://host.docker.internal:58878  --insecure-skip-tls-verify=true apply -f ./k8s/configmap.yaml --validate=false'
                    sh 'kubectl --token $token --server https://host.docker.internal:58878  --insecure-skip-tls-verify=true apply -f ./k8s/credentials.yaml --validate=false'
                    sh 'kubectl --token $token --server https://host.docker.internal:58878  --insecure-skip-tls-verify=true apply -f ./k8s/pv.yaml --validate=false'
                    sh 'kubectl --token $token --server https://host.docker.internal:58878  --insecure-skip-tls-verify=true apply -f ./k8s/pvc.yaml --validate=false'
                    sh 'kubectl --token $token --server https://host.docker.internal:58878  --insecure-skip-tls-verify=true apply -f ./k8s/deployment.yaml --validate=false'
                    sh 'kubectl --token $token --server https://host.docker.internal:58878  --insecure-skip-tls-verify=true apply -f ./k8s/service.yaml --validate=false'
                }
            }
        }
    }
}
