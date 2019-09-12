pipeline{
    agent none
    stages{
        stage("Get Code from Git"){
            agent { label 'master' }
            steps{
               git 'https://github.com/alvaro980/Docker-files.git'
            }  
        }
        // stage("Build"){
        //     agent { docker 'maven:3-alpine' }
		// 	steps{
        //          sh "mvn clean package"
        //     }
        // }
        // stage("Archive artifact"){
        //     agent { label 'master' }
        //     steps{
        //        archiveArtifacts 'target/*.jar'
        //     }
        // }
		// stage("Package"){
        //     agent { label ' master' }
        //     steps{
        //        sh "docker build -t blog_app:v1 ."
        //        sh "docker save -o blog.tar blog_app:v1"
        //        stash name: "stash-artifact", includes: "blog.tar"
        //     }
        // }
    //     stage("Deploy to QA"){
    //         agent { label ' master' }
    //         steps{
    //             sh "docker rm blog -f || true"
    //             sh "docker-compose up -d book_app:v1"
    //         }
    //     }
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
    // }
}