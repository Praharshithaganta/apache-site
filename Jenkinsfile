pipeline {
    agent any

    stages {
        stage('Checkout Code') {
            steps {
                git 'https://github.com/<your-username>/apache-site.git'
            }
        }

        stage('Build Docker Image') {
            steps {
                sh 'docker build -t apache-site:latest .'
            }
        }

        stage('Run Container') {
            steps {
                sh 'docker rm -f apache-site || true'
                sh 'docker run -d -p 8080:80 --name apache-site apache-site:latest'
            }
        }
    }
}
