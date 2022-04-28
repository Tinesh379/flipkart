pipeline{
    agent any
    environment{
        buildVesrion = ""
    }
    options {
  timeout(5)
  buildDiscarder logRotator(artifactDaysToKeepStr: '1', artifactNumToKeepStr: '4', daysToKeepStr: '', numToKeepStr: '4')
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
                echo "package version is ${assignBuildVersion()}"
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

def assignBuildVersion(){
    return env.BRANCH_NAME == 'main'? "${env.BUILD_NUMBER}" : "${env.BUILD_NUMBER}-SNAPSHOT"
}
