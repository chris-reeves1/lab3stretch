pipeline {
    agent any

    stages {
         stage('Init') {
            steps {
                sh 'docker stop myapp || true'
                sh 'docker rm myapp || true'
            }
        }
        stage('Build') {
            steps {
                sh 'docker build -t myapp .'
            }
        }

        stage('Deploy') {
            steps {
                sh 'docker run -d -p 5500:5500 myapp:latest'
            }
        }
    }
}

