pipeline {
    agent any

    stages {
        stage('List WorkSpace') {
            steps {
                echo 'Listing WorkSpace..'
                sh 'ls'
                
            }
        }
        stage('Cat a file') {
            steps {
                sh 'cat deploy-tomcat.yml'
            }
        }
        stage('Find the OS') {
            steps {
                 sh 'uname -a'
            }
            
        stage('List the processing table... and .. disk usage ..') {
            steps {
                 sh 'ps -ae'
                 sh 'df -h'
            }    
            
        }
    }
}
