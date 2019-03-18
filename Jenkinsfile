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
                sh 'cat Tomcat-Ansible-Role'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
}
