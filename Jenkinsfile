pipeline {
    agent none
    environment {
        DOCKERHUB_CREDENTIALS = credentials("cb26ac19-f954-40ca-a12e-d790594bcca7")
    }
    stages {
        stage('git') {
            agent {
                label "K8-Master"
            }
            steps {
                script {
                    git 'https://github.com/Virat-0410/project.git'
                }
            }
        }
        stage('docker') {
            agent {
                label "K8-Master"
            }
            steps {
                script {
                    sh 'sudo docker build . -t aadi0410/project-2'
                    sh 'sudo docker login -u ${DOCKERHUB_CREDENTIALS_USR} -p ${DOCKERHUB_CREDENTIALS_PSW}'
                    sh 'sudo docker push aadi0410/project-2'
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
