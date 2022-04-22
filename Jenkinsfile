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
            when{
                branch 'main'
                beforeAgent true
            }
        }
    }
}