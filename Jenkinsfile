#!groovy

//def tools = new org.devops.tools()

String srcUrl = "${env.SrcUrl}"
String BranchName = "${env.BranchName}"
String buildType = "${env.buildType}"
String buildShell = "${env.buildShell}"

String workspace = "/opt/jenkins/workspace"

String Sub_dir ="${env.Sub_dir}"

pipeline {
    agent any
    tools{
        maven 'maven-3.8.6'
    }
    stages{
        stage ('mcwtest') {
            steps {
                echo "Running ${env.BUILD_NUMBER} on ${env.JENKINS_URL}" // 方法一
                echo "Running $env.BUILD_NUMBER on $env.JENKINS_URL" // 方法二
                echo "Running ${BUILD_NUMBER} on ${JENKINS_URL}" // 方法三
                echo "========>printenv:"
                sh "printenv"
            }
        }
        stage('Git pull') {
            steps {
                // 下载代码
                git branch: 'main', credentialsId: '76d8bab0-4561-4373-a11d-b351e1e0536a', url: 'https://github.com/yuezu1026/mock-client.git'
            }
        }
        // stage('Checkout'){
        //     steps{
        //         git branch:'main',url:'https://github.com/yuezu1026/mock-client.git'
        //     }
        // }
        stage('build'){
            steps{
                sh 'mvn clean compile'
            }
        }
        stage('Example'){
            steps{
                script {
                    if(env.BRANCH_NAME == 'main'){
                        echo 'I only execute on the master branch'
                    }else{
                        echo 'I execute elsewhere'
                    }
                }
            }
            
        }
    }    
}