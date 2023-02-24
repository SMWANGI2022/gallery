 pipeline{
    agent any
    tools{
            nodejs "node"
    }
    stages{
        stage('Clone repository'){
            steps{
                git 'https://github.com/SMWANGI2022/gallery'
            }
        }
        stage('Build'){
            steps{
                sh 'npm install' 
                sh "yarn"
            }
        }
        stage('Test'){
            steps{
                sh 'npm test' 
            }
        }
        stage('Deploy to Heroku'){
           steps{
               withCredentials([usernameColonPassword(credentialsId:'heroku', variable:'HEROKU_CREDENTIALS')]){
               sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/moringa-gallery-backend.git master'
                }
                slackSend channel: 'jenkins', message: 'jenkins syntax'
           }
        }
        
    }
    post {
     failure {
      emailext body: 'pipeline syntax', subject: 'jenkins', to: 'susan.mwangi3@gmail.com'
     }
    }
}
