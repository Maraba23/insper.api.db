
// minikube start --driver=docker --profile=store

pipeline {
    agent any
    stages {
        stage('Deploy on k8s') {
            steps {
                withCredentials([ string(credentialsId: 'minikube-credentials', variable: 'token') ]) {
                    sh 'kubectl --token eyJhbGciOiJSUzI1NiIsImtpZCI6IjlaZHF4NlYwdktabHJSNDQzVHpTMEt6QnVGVTdqWXVmZGZrMEdGZ0kwTlEifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhYpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJkZWZhdWx0Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQub6Implb2NvdW50Iiwia3ViZXJuZXRlcy5pbymFtZSI6ImplbmtpbnMtdG9rZW4iLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoiamVua2lucyIsImt1YmVybmV0ZXMuaW8vc2V1bnQvcVzLmlvL3NlcnZpY2VhY2NvdW50L3NydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6ImYwODgwNGYxLTNlNGYtNGIyYS1iNDRjLTY1ZDE4ZTQxNDMzYiIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudpbnMifjLTY1ZDE4ZTQxNDMzYiIsInN1YiI6DpkZWZhdWx0OmplbmtpbnMifQ.f5iIJBnMXu5bp-EUbavmlAHk0AUV0LUBqylUUPp-TexzY_xgIQ2kRkBro27mdCTSmZ-2o_ppTpOeoDqRAcSz7a0eRatjK5weu5tVerhjahiWUpxUNra0eRatjK5weu5tVerhjahiWTWpzJaTWpzJawr16pHFU3FU_INakgFUpxUNrGtWye0Rjubv2lAN1m8o5ZRryYk0QQkM5SFuIFGZWz2ChBcgp84nNgScPfOxPwHgvYpLkT8QOqe-SqJdBjY3_Leu_1IowmhyJpf1GJZvqWb0xFquEf3XxCQRiNOsulqjVWb0xFqnamp2mjr-boZHp52suEf3XxCQRiNOsulqjVWb0xFqnamp2_QMYRxBnsvaMn0uWgXdRQeoCt5qvHnkxKfdrskDLALmSKmqrZnQbwhvRC_Q --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/configmap.yaml '
                    sh 'kubectl --token eyJhbGciOiJSUzI1NiIsImtpZCI6IjlaZHF4NlYwdktabHJSNDQzVHpTMEt6QnVGVTdqWXVmZGZrMEdGZ0kwTlEifQ.eyJpc3MiOiJrdWJlcm5ldGVzL3NlcnZpY2VhYpY2VhY2NvdW50Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9uYW1lc3BhY2UiOiJkZWZhdWx0Iiwia3ViZXJuZXRlcy5pby9zZXJ2aWNlYWNjb3VudC9zZWNyZXQub6Implb2NvdW50Iiwia3ViZXJuZXRlcy5pbymFtZSI6ImplbmtpbnMtdG9rZW4iLCJrdWJlcm5ldGVzLmlvL3NlcnZpY2VhY2NvdW50L3NlcnZpY2UtYWNjb3VudC5uYW1lIjoiamVua2lucyIsImt1YmVybmV0ZXMuaW8vc2V1bnQvcVzLmlvL3NlcnZpY2VhY2NvdW50L3NydmljZWFjY291bnQvc2VydmljZS1hY2NvdW50LnVpZCI6ImYwODgwNGYxLTNlNGYtNGIyYS1iNDRjLTY1ZDE4ZTQxNDMzYiIsInN1YiI6InN5c3RlbTpzZXJ2aWNlYWNjb3VudpbnMifjLTY1ZDE4ZTQxNDMzYiIsInN1YiI6DpkZWZhdWx0OmplbmtpbnMifQ.f5iIJBnMXu5bp-EUbavmlAHk0AUV0LUBqylUUPp-TexzY_xgIQ2kRkBro27mdCTSmZ-2o_ppTpOeoDqRAcSz7a0eRatjK5weu5tVerhjahiWUpxUNra0eRatjK5weu5tVerhjahiWTWpzJaTWpzJawr16pHFU3FU_INakgFUpxUNrGtWye0Rjubv2lAN1m8o5ZRryYk0QQkM5SFuIFGZWz2ChBcgp84nNgScPfOxPwHgvYpLkT8QOqe-SqJdBjY3_Leu_1IowmhyJpf1GJZvqWb0xFquEf3XxCQRiNOsulqjVWb0xFqnamp2mjr-boZHp52suEf3XxCQRiNOsulqjVWb0xFqnamp2_QMYRxBnsvaMn0uWgXdRQeoCt5qvHnkxKfdrskDLALmSKmqrZnQbwhvRC_Q --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/credentials.yaml '
                    sh 'kubectl --token $token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/pv.yaml'
                    sh 'kubectl --token $token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/pvc.yaml '
                    sh 'kubectl --token $token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/deployment.yaml'
                    sh 'kubectl --token $token --server https://host.docker.internal:${env.K_PORT}  --insecure-skip-tls-verify=true apply -f ./k8s/service.yaml'
                }
            }
        }
    }
}
