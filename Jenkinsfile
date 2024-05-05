pipeline {
    agent any

    stages {
        stage('Build & Tag Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker1', url: 'https://hub.docker.com/u/ajdeepak45, toolName: 'docker')  {
                        sh "docker build -t ajdeepak45/productcatalogservice:latest ."
                    }
                }
            }
        }
        
        stage('Push Docker Image') {
            steps {
                script {
                    withDockerRegistry(credentialsId: 'docker1', url: 'https://hub.docker.com/u/ajdeepak45, toolName: 'docker') {
                        sh "docker push ajdeepak45/productcatalogservice:latest "
                    }
                }
            }
        }
    }
}
