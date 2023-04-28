pipeline {
    agent any
    stages {
        // stage('repo') {
        //     steps {
        //         script {
        //             git branch: 'main', url: 'https://github.com/JuanDavRH/deploy-nginx.git'
        //         }
        //     }
        // }
        stage('docker build') {
            steps {
                script {
                    sh "sudo docker build -t juanrodriguez20/apuntes:3.0-${BUILD_ID} ."
                }
            }
        }
        stage('docker run') {
            steps {
                script {
                    sh "sudo docker run -dp 80:80 --name contenedor juanrodriguez20/apuntes:3.0-${BUILD_ID} "
                }
            }
        }
        stage('docker push') {
            steps {
                script {
                    sh "sudo docker push juanrodriguez20/apuntes:3.0-${BUILD_ID}"
                }
            }
        }
        
    }
}
  