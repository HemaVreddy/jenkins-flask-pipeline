pipeline {
    agent any
    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    docker.build("Hemalatha98/jenkins-flask")
                }
            }
        }
        stage('Push to DockerHub') {
            steps {
                script {
                    docker.withRegistry('https://index.docker.io/v1/', 'dockerhub-creds') {
                        docker.image("your-dockerhub-username/jenkins-flask").push("latest")
                    }
                }
            }
        }
    }
}

