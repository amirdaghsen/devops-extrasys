pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

    stages {

        stage('Checkout Code') {
            steps {
                checkout scm
            }
        }

        stage('Verify Tools') {
            steps {
                sh 'mvn -v'
            }
        }

        stage('Build Project') {
            steps {
                    dir('event-app') {
            sh 'mvn clean install -DskipTests'
}            }
        }
    }
}
