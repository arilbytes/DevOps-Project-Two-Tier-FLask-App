pipeline{
    agent any
    stages{
        stage('Clone repo'){
            steps{
                git branch: 'main', url: 'https://github.com/arilbytes/DevOps-Project-Two-Tier-FLask-App.git'
            }
        }
        stage('Build image'){
            steps{
                sh 'docker build -t flask-app .'
            }
        }
        stage('Deploy with docker compose'){
            steps{
                //Existing container if they're running
                sh 'docker compose down || true'
                sh 'docker compose up -d --build'
            }
        }
    }
}