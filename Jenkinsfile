@Library('shared') _
pipeline{
    agent any
    stages{
        stage('code'){
            steps{
                script{
                    clone('https://github.com/Tandon77ayush/two-tier-flask-app.git', 'master')
                }
            }
        }
        stage('build'){
            steps{
                sh 'docker compose down'
                sh 'docker build -t flaskapp .'
            }
        }
        stage('deploye'){
            steps{
                sh 'docker compose up -d'
            }
        }
        stage('finished sucsessfully'){
            steps{
                echo "finished sucsessfully"
            }
        }
    }
    post{
        success{
            emailext subject: "flask-pipeline",
                     to: "tandonayush350@gmail.com",
                     body: "pipeline is build succesfuly"
        }
        failure{
            emailext subject: "flaskpipeline",
                     to: "tandonayush350@gmail.com",
                     body: "pipeline build is failed"
        }
    }
}
