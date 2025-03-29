pipeline {
    agent any
    environment{
        GREETING ="Hello"
    }
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
        stage("打招呼"){
            steps{
                sh 'echo "$GREETING $TITLE"'
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