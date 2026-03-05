pipeline {
    agent any

    tools {
        maven 'Maven3'
    }

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
stage('Test & Coverage') {
    steps {
        sh 'mvn clean test'
    }
}

stage('Archive Test Results') {
    steps {
        junit 'target/surefire-reports/*.xml'
        archiveArtifacts 'target/site/jacoco/*'
    }
}
       
            }
        }

    }
}
