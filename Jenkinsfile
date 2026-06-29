pipeline {
    agent any

    stages {
        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/saikauthale/sonarqube.git'
            }
        }

        stage('List Files') {
            steps {
                sh 'pwd'
                sh 'ls -la'
            }
        }
    }
}
