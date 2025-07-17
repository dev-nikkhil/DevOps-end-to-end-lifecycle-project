pipeline {
    agent none
    environment {
        DOCKERHUB_CREDENTIALS = credentials("crdentials")
    }
    stages {
        stage('git') {
            agent {
                label "K8-Master"
            }
            steps {
                script {
                    git 'https://github.com/repo/'
                }
            }
        }
        stage('docker') {
            agent {
                label "K8-Master"
            }
            steps {
                script {
                    sh 'sudo docker build . -t image'
                    sh 'sudo docker login -u ${DOCKERHUB_CREDENTIALS_USR} -p ${DOCKERHUB_CREDENTIALS_PSW}'
                    sh 'sudo docker push image'
                }
            }
        }
        stage('kubernetes') {
            agent {
                label "K8-Master"
            }
            steps {
                script {
                    sh 'kubectl delete deploy my-deployment'
                    sh 'kubectl apply -f deploy.yaml'
                    sh 'kubectl delete service my-service'
                    sh 'kubectl apply -f service.yaml'
                }
            }
        }
    }
}
