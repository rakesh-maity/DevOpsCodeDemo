pipeline{
    tools{
        maven 'PVMaven'
    }
    agent any
    stages{
        stage('1.CloneRepo'){
            steps{
                git 'https://github.com/rakesh-maity/DevOpsCodeDemo.git'
            }
        }
        stage('2.CodeCompile'){
            steps{
                sh 'mvn compile'
            }
        }
        stage('3.CodeReview'){
            steps{
                sh 'mvn pmd:pmd'
            }
        }
        stage('4.CodeTest'){
            steps{
                sh 'mvn test'
            }
            post{
                success{
                    junit 'target/surefire-reports/*.xml'
                }
            }
        }
        stage('5.CodePackage'){
            steps{
                sh 'mvn package'
            }
        }
        
    }
}
