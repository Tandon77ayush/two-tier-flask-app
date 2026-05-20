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
        stage('finished sucsessfully'){
            steps{
                echo "finished sucsessfully"
            }
        }
    }
    post{
        success{
            emailext subject: "success",
                     to: "tandonayush350@gmail.com",
                     body: "pipeline is build succesfuly"
        }
    }
}
