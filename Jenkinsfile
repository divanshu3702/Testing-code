pipeline {
    agent any

    stages {

        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/divanshu3702/Testing-code.git'
            }
        }

        stage('Build') {
            steps {
                bat 'mvn clean package'
            }
        }

        stage('Unit Tests + Coverage') {
            steps {
                bat 'mvn test'
            }
        }

        stage('Archive Coverage Report') {
            steps {
                archiveArtifacts artifacts: 'target/site/jacoco/**'
            }
        }
    }
}
