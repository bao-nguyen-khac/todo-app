pipeline {
    agent any
    tools {nodejs "NodeJS" }
    stages {
        
        stage('Build') { 
            steps {
                sh 'npm install --production' 
            }
        }
        stage('Test') {
            steps {
                sh 'npm test'
            }
        }
        // stage('Push image'){
        //     steps {
        //         withDockerRegistry(credentialsId: 'docker-hub', url: 'https://index.docker.io/v1/') {
        //             // some block
        //             sh 'docker build -t khacbaocsek19/todo-app:v2 .'
        //             sh 'docker push khacbaocsek19/todo-app:v2'
        //         }
        //     }
        // }
        // stage('Ssh k8s-master'){
        //     steps{
        //         sshagent(['ssh-k8s-master']) {
        //             // some block
        //             sh 'ssh -o StrictHostKeyChecking=no -p 9922 -l ubuntu 61.28.232.236 kubectl set image deployment/todo-app-backend todo-app-backend=khacbaocsek19/todo-app:v2'
        //         }
        //     }
        // }
    }
}