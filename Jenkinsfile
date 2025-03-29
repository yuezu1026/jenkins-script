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
        stage('build'){
            steps{
                sh 'mvn -B -DskipTests clean package' 
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