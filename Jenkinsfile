
pipeline {
    agent any

    environment {
        DOCKER_BUILDKIT = '1'
    }

    stages {
        stage('Checkout SCM') {
            steps {
                git url: 'https://github.com/Ravina-Duggal/seedlyfrontend.git',
                    branch: 'main'
            }
        }

        stage('Build') {
            steps {
                sh 'docker build -t frontend .'
            }
        }

        stage('Cleanup') {
            steps {
                sh 'docker rm -f frontend-container || true'
            }
        }

        stage('Start') {
            steps {
                sh 'docker run -d --name frontend-container -p 5173:5173 frontend'
            }
        }
    }
}
