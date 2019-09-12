pipeline{
    agent {
        docker {
            image 'node:latest'
            image 'mongo'
        }
    }
    stages{
        stage("Get Code from Git"){
            steps{
               git 'https://github.com/alvaro980/JavaScript.git'  
        }
        stage("Build"){
            steps{
                 sh "sudo docker run -d -p 27017-27019:27017-27019 --name mongodb mongo"
                 sh "sudo docker run -d -p 4000:4000 --name web_app node" 
                 sh "npm install"     
        }
        stage("Deploy to QA"){
            steps{
                 sh "npm run dev"     
        }
        stage("Get Automation Code from Git"){
            steps{
               git 'https://github.com/susana-lima/auto-GA-v07/tree/books-app-auto-devops'
        }
        stage("Run Automation tests"){
            steps{
                dir("auto-GA-v07"){
                    sh "sudo ./gradlew build"  
                    sh "gradlew test"   
                }  
        }
         stage("Generate Automation report"){
            steps{
                cucumber buildStatus: 'UNSTABLE',
                fileIncludePattern: 'target/*.json',
                trendsLimit: 10,
                classifications: [
                    [
                        'key': 'Browser',
                        'value': 'Chrome'
                    ]
                ]
        }
        stage("Deploy PROD"){
            steps{
                sh "sudo docker network create -d overlay appoverlay1"
                sh "sudo docker service create --name webapp -d --network appoverlay1 -p 4000:4000 hshar/webapp"
            }
    }
}