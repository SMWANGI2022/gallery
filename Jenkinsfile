pipeline{
	agent any
	tools{
	    nodejs "node"
	}
	stages{
	    stage('Clone Repo'){
	      steps{
	        git 'https://github.com/SMWANGI2022/gallery'
	       }
	    }
	    stage('Build'){
	      steps{
	        sh 'npm install'
	      }
	    }
        stage('Deploy to Heroku'){
	        steps{
	            withCredentials([usernameColonPassword(credentialsId:'heroku', variable:'HEROKU_CREDENTIALS')]){
	            sh 'git push https://${HEROKU_CREDENTIALS}@git.heroku.com/moringa-gallery-backend.git master'}
	        }
	    }
	}
}