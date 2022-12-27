pipeline {
    agent any
    tools {
        maven 'Maven_Home'
        jdk 'JDK'

    }
    stages {
        stage ('Initialize') {
            steps {
                bat '''
                    echo "PATH = ${PATH}"
                    echo "MAVEN_HOME = ${MAVEN_HOME}"
                '''
            }
        }

        stage ('Build') {
            steps {
                bat 'mvn -Dmaven.test.failure.ignore=true install clean compile' 
            }
            post {
                success {
                    junit 'target/surefire-reports/**/*.xml' 
                }
            }
        }
    }
}