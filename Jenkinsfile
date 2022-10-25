pipeline {
    agent any
    tools { nodejs "NodeJS" }
    stages {
        stage('Build') { 
            steps {
                sh 'npm install --omit=dev' 
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        stage('Build and push docker image'){
            steps {
                withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
                    sh 'docker build -t khacbaocsek19/todo-app:v4 .'
                    sh 'docker push khacbaocsek19/todo-app:v4'
                }
            }
        }
        stage('Continuous deployment in k8s'){
            steps{
                sshagent(['main-root']) {
                    // some block
                    sh 'ssh -o StrictHostKeyChecking=no -l root 35.185.184.61 kubectl set image deployment/todo-app-backend todo-app-backend=khacbaocsek19/todo-app:v4'
                }
            }
        }
    }
}