pipeline {

    agent any

    tools {
    jdk 'JDK17'
}
    }

    environment {

        DEPLOY_DIR="/var/www/html"

    }

    stages {

        stage('Clone') {

            steps {

                git 'https://github.com/saikauthale/sonarqube.git'

            }

        }

        stage('SonarQube Scan') {

            steps {

                withSonarQubeEnv('Sonar') {

                    sh '''

                    sonar-scanner \
                    -Dsonar.projectKey=calculator \
                    -Dsonar.sources=. \
                    -Dsonar.host.url=$SONAR_HOST_URL \
                    -Dsonar.login=$SONAR_AUTH_TOKEN

                    '''

                }

            }

        }

        stage('Deploy') {

            steps {

                sh '''

                sudo cp -r * $DEPLOY_DIR

                '''

            }

        }

    }

}
