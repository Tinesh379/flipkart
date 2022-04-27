pipeline{
    agent any
    environment{
        buildVesrion = ""
    }
    stages{
        stage('tools'){
            steps{

                bat 'mvn -v'
                bat 'git version'
            }
           
        }
        stage('test'){
            steps{
                  echo 'Hello world'
            }
        }
        stage('Build Num'){
            steps{
                echo "${env.buildVersion}"
                echo "${env.BUILD_NUMBER}"
            }
        }
    }
    post{
        success{
            script{
                println "This is Windows Machine"
            }
        }
    }
}