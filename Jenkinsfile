pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                echo 'Building Docker image for Polanki...'
                sh 'docker build -t polanki-nginx-site .'
            }
        }

        stage('Run Docker Container') {
            steps {
                echo 'Running container for Task 2...'
                sh 'docker run -d -p 8080:80 --name polanki-nginx-container polanki-nginx-site'
            }
        }
    }
}
