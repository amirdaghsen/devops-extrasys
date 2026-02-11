pipeline {
    agent any

    tools {
        maven 'Maven3'
        jdk 'JDK17'

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
            dir('eventsProject') {
    sh 'echo "JAVA HOME = $JAVA_HOME"'
    sh 'which java'
    sh 'java -version'
    sh 'mvn -version'
    sh 'mvn clean install -DskipTests'
}

                       }
        }
    }
}
