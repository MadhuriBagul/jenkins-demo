pipeline {
    agent any

    stages {

        stage('Build Image') {
            steps {
                sh 'podman build -t myapp .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'podman rm -f myapp-container || true'
                sh 'podman run -d -p 8081:80 --name myapp-container myapp'
            }
        }
    }
}