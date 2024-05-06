pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    dir('src') {
                        withDockerRegistry(credentialsId: 'docker1', toolName: 'docker') {
                            sh "docker build -t ajdeepak45/cartservice:latest ."
                        }
                    }
                }
            }
        }

        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker1', toolName: 'docker') {
                        sh "docker push ajdeepak45/cartservice:latest"
                    }
                }
            }
        }
    }
}
