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
        stage('Assign Build Version'){
            steps{
                env.buildVersion = ${env.BUILD_NUMBER}
                echo "${env.buildVersion}"
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