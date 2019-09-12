pipeline{
    agent none
    stages{
        stage("Get Code from Git"){
            agent { label 'master' }
            steps{
               git 'https://github.com/mgviscarra/copa_america'
            }
            
        }
        stage("Build"){
            agent { label 'master' }
			steps{
                sh "mvn clean package"
            }
        }
        stage("Archive artifact"){
            agent { label 'master' }
            steps{
               archiveArtifacts 'target/*.jar'
			   
            }
        }
    }
}