#!groovy

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
        stage('Checkout'){
            steps{
                git branch:'main',url:'https://github.com/yuezu1026/mock-client.git'
                git clone git@github.com:yuezu1026
            }
        }
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