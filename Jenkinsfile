pipeline{
    agent any
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
    }
    post{
        success{
            script{
                println "This is Windows Machine"
            }
        }
    }
}