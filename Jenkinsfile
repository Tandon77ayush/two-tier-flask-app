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
              script{
                  build('flaskapp')
              }
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
       mail('flask-pipeline status','tandonayush350@gmail.com','pipeline is biuld successfully','pipeline build is failed')
    }
}
