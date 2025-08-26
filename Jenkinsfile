pipeline {
    agent any
    tools {
        maven 'maven3'
        jdk 'java11'
    }
    stages {
        stage('checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AbdullahGhous78623/addressbook-cicd-abdullah.git'
            }
        }
        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }
        stage("deploy the project on tomcat") {
            steps {
                sh 'ansible-playbook -i inventory.ini deploy-tomcat.yml'
            }
        }
    }
}
