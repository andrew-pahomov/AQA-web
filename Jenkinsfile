#!groovy
pipeline {
    agent {
        label 'master'
    }
    stages {
        stage("grant permissions") {
            steps {
                sh 'chmod +x gradlew'
            }
        }
        stage("start SUT") {
            steps {
                sh 'java -jar ./artifacts/app-order.jar &'
            }
        }
        stage("start tests") {
            steps {
                sh './gradlew test --info'
            }
        }
    }
}