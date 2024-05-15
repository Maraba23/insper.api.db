
// minikube start --driver=docker --profile=store

pipeline {
    agent any
    stages {

        stage('Build Image') {
            steps {
                script {
                    discovery = docker.build("pasilva2023/db:${env.BUILD_ID}", "-f Dockerfile .")
                }
            }
        }

        stage('Push Image') {
            steps {
                script {
                    docker.withRegistry('https://registry.hub.docker.com', 'dockerhub-credential') {
                        discovery.push("${env.BUILD_ID}")
                        discovery.push("latest")
                    }
                }
            }
        }

        stage('Deploy on k8s') {
            steps {
                withCredentials([ string(credentialsId: 'minikube-credentials', variable: 'api_token') ]) {
                    sh 'kubectl --token $api_token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/configmap.yaml '
                    sh 'kubectl --token $api_token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/credentials.yaml '
                    sh 'kubectl --token $api_token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/pv.yaml'
                    sh 'kubectl --token $api_token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/pvc.yaml '
                    sh 'kubectl --token $api_token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/deployment.yaml'
                    sh 'kubectl --token $api_token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/service.yaml'
                }
            }
        }
    }
}