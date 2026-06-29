pipeline {
    agent any

    stages {

        stage('Clone') {
            steps {
                git branch: 'main', url: 'https://github.com/saikauthale/sonarqube.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo cp -r index.html style.css script.js /var/www/html/
                '''
            }
        }
    }
}
