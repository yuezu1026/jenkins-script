pipeline {
    agent any
    stages{
        stage("Hello"){
            steps{
                echo "Hello world"
            }
        }
        stage("Hello2"){
            steps{
                echo "Hello world2"
            }
        }
        stage("Hello3"){
            steps{
                echo "Hello world3"
            }
        }
    }
    post{
        aborted {
            echo "构建被终止"
        }
        success {
            echo "构建成功"
        }
        failure{
            echo "构建失败"
        }
    }
}