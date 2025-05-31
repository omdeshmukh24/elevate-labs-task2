pipeline {
    agent any

    environment {
        DOCKER_IMAGE = "your-dockerhub-username/nodejs-demo-app"
    }

    stages {
        stage('Clone Repo') {
            steps {
                git 'https://github.com/your-username/nodejs-demo-app.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                script {
                    sh "docker build -t $DOCKER_IMAGE ."
                }
            }
        }

        stage('Push to DockerHub') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'dockerhub-creds', usernameVariable: 'USERNAME', passwordVariable: 'PASSWORD')]) {
                    sh "echo $PASSWORD | docker login -u $USERNAME --password-stdin"
                    sh "docker push $DOCKER_IMAGE"
                }
            }
        }

        stage('Deploy (Manual or SSH)') {
            steps {
                echo 'Deploy step (e.g., SSH to EC2 and restart container)'
            }
        }
    }
}
