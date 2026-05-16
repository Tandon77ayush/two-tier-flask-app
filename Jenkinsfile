pipeline{
    agent any
    stages{
        stage('code'){
            steps{
                git url: 'https://github.com/Tandon77ayush/two-tier-flask-app.git'
            }
        }
        stage('build'){
            steps{
                sh 'docker build -t flaskapp .'
            }
        }
        stage('deploye'){
            steps{
                sh 'docker compose up -d'
            }
        }
    }
}
