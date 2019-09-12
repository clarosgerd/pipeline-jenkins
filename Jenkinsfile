pipeline{
    agent none
    stages{
        stage("Get Code from Git"){
            agent { label 'master' }
            steps{
               git 'https://github.com/alvaro980/Docker-files.git'
            }  
        }
        stage("Deploy to QA"){
            agent { label ' master' }
            steps{
                dir("Docker-files"){
                     sh "pwd"
                     sh "ls"
                     sh "docker-compose up --d"    
                }
            }
        }
    //     stage("Get Automation Code from Git"){
    //         agent { label 'master' }
    //         steps{
    //            git 'https://github.com/susana-lima/auto-GA-v07/tree/books-app-auto-devops'
    //         } 
    //     }
    //     stage("Run Automation tests"){
    //         agent { label 'master' }
    //         steps{
    //             sh "docker rm browser -f || true"
    //             sh "docker run -d -p 4444:4444 --name browser --link blog selenium/standalone-chrome"
    //             sh "mvn test"
    //         }  
    //     }
    //      stage("Generate Automation report"){
    //         agent{label "master"}
    //         steps{
    //             cucumber buildStatus: 'UNSTABLE',
    //             fileIncludePattern: 'target/*.json',
    //             trendsLimit: 10,
    //             classifications: [
    //                 [
    //                     'key': 'Browser',
    //                     'value': 'Chrome'
    //                 ]
    //             ]
    //         }
    //     }

    //     stage("Deploy PROD"){
    //         agent{label "PROD"}
    //         steps{
    //             unstash "stash-artifact"
    //             sh "docker load -i blog.tar"
    //             git 'https://github.com/alvaro980/Docker-files.git'
    //             sh "docker-compose up -d book_app:v1"
    //         }
    //     }
    }
}