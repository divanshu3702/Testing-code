pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git 'https://github.com/divanshu3702/Testing-code.git'
            }
        }

        stage('Build') {
            steps {
                sh 'mvn clean package'
            }
        }

        stage('Unit Tests + Coverage') {
            steps {
                sh 'mvn test'
            }
        }

        stage('Archive Coverage Report') {
            steps {
                archiveArtifacts artifacts: 'target/site/jacoco/**'
            }
        }
    }
}
