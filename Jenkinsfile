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
            }
        }
      
    }
    
    }