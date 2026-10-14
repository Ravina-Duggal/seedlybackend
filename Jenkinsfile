pipeline{
    agent any
    stages{
        stage('git clone'){
            steps{
                git url: 'https://github.com/Ravina-Duggal/seedlybackend.git' , branch: 'main'
            }
        }
        stage('build'){
            steps{
                sh "docker build -t backend ."
            }
        }
        stage('cleanup'){
            steps{
                sh "docker stop backend || true"
                sh "docker rm backend || true"
            }
        }
        stage('run'){
            steps{
                sh "docker run -d --name backend-container -p 3000:3000 backend"
            }
        }
    }
}
