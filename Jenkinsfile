pipeline {
    agent any

    tools {
        // Use the Maven tool configured in Jenkins
        maven 'Maven3'
        // Use JDK 17 configured in Jenkins global tools
        jdk 'JDK17'
    }

    environment {
        // Optional: force JAVA_HOME in case container overrides it
        JAVA_HOME = '/usr/lib/jvm/java-17-openjdk-amd64'
        PATH = "${JAVA_HOME}/bin:${env.PATH}"
    }

    stages {
        stage('Build') {
    steps {
        dir('eventsProject') {
            sh '''
            export JAVA_HOME=/usr/lib/jvm/temurin-17-jdk-amd64
            export PATH=$JAVA_HOME/bin:$PATH

            echo "=== FORCED JAVA ==="
            echo $JAVA_HOME
            which java
            java -version

            mvn clean package -DskipTests
            '''
        }
    }
}


    }
}
