pipeline {
    agent any

    stages {
        stage ('Setup Stage') {

            steps {
                withMaven(maven : 'maven_3_8_6') {
                    sh 'mvn clean'
                }
            }
        }
        stage ('Compile Stage') {

            steps {
                withMaven(maven : 'maven_3_8_6') {
                    sh 'mvn compile'
                }
            }
        }


        stage ('UnitTesting Stage') {
            steps {
                withMaven(maven : 'maven_3_8_6') {
                    sh 'mvn test'
                }
            }
        }
    }
}