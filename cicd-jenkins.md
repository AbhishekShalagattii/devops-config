
pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/AbhishekShalagattii/java-devops-app.git'
            }
        }

        stage('Build') {
            steps {
                bat 'javac demo.java'
            }
        }

        stage('Run Application') {
            steps {
                bat 'java demo'
            }
        }

    }
}
