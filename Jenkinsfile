pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh 'docker build -t my-web .'
            }
        }

        stage('Run') {
            steps {
                sh 'docker stop my-web-container || true'
                sh 'docker rm my-web-container || true'
                sh 'docker run -d -p 8080:80 --name my-web-container my-web'
            }
        }
    }
}
