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
                sh 'docker build -t seedlyfrontend .'
            }
        }
        stage('start'){
            steps{
                sh 'docker run -d -p 5173:5173 seedlyfrontend'
            }
        }
    }
}
