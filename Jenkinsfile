pipeline{
    agent any
    stages{
        stage('cloning the git repo'){
            steps{
                git url: 'https://github.com/Ravina-Duggal/seedlyfrontend.git', branch:'main'
            }
        }
        stage('build'){
            steps{
                sh 'docker build -t frontend .'
            }
        }
        stage('cleanup'){
            steps{
                sh "docker stop frontend-container || true"
                sh "docker rm frontend-container || true"
            }
        }
        stage('start'){
            steps{
                sh 'docker run -d --name frontend-container -p 5173:5173 frontend'
            }
        }
    }
}
