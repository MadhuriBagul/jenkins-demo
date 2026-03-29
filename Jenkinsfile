pipeline {
    agent any

    stages {

        stage('Clone Code') {
            steps {
                git 'https://github.com/MadhuriBagul/jenkins-demo.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'podman build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'podman run -d -p 8081:80 --name myapp-container myapp || true'
            }
        }
    }
}