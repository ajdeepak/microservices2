pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker1', toolName: 'docker') {
                        sh "docker build -t ajdeepak45/adservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker1', toolName: 'docker') {
                        sh "docker push adeepak45/adservice:latest "
                    }
                }
            }
        }
    }
}
