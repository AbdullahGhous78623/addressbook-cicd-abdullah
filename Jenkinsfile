pipeline {
    agent any

    tools {
        maven 'maven3'   // Make sure this matches the Jenkins Maven tool name
        jdk 'java11'     // Make sure this matches the Jenkins JDK tool name
    }

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/AbdullahGhous78623/addressbook-cicd-abdullah.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Deploy to EC2') {
            steps {
                // No inventory.ini needed; using default /etc/ansible/hosts
                sh 'ansible-playbook /etc/ansible/deploy-tomcat.yml'
            }
        }
    }
}
av
