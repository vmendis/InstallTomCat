pipeline {
    agent any

    stages {
        stage('List WorkSpace') {
            steps {
                echo 'Listing WorkSpace..'
                sh 'ls'
                sh 'ansible --version'
            }
        }
        stage('Cat a file') {
            steps {
                sh 'cat deploy-tomcat.yml'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
