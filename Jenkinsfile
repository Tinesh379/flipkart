pipeline{
    agent any
    stages{
        stage('tools'){
            bat 'mvn -v'
            bat 'git version'
        }
        stage('test'){
            echo 'Hello world'
        }
    }
}