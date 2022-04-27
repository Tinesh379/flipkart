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
        stage('status'){
            steps{
                echo '${env.buildVersion}'
                echo '${env.BUILD_NUMBER}'
                script{
                    if(${currentBuild.result} == "SUCCESS"){
                        env.buildVesrion = ${env.BUILD_NUMBER}
                        println "$buildVersion"
                    }
                    else{
                        println "build status is not ok"
                    }
                }
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