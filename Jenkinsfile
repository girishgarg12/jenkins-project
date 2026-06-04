pipeline {

    agent any

    stages {

        stage('Build') {
            steps {
                echo 'Compiling Project'
                bat 'mvn clean compile'
            }
        }

        stage('Test') {
            steps {
                echo 'Running Tests'
                bat 'mvn test'
            }
        }

        stage('Package') {
            steps {
                echo 'Packaging JAR'
                bat 'mvn package'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'target/*.jar'
            }
        }
    }

    post {

        success {
            echo 'Build Successful'
        }

        failure {
            echo 'Build Failed'
        }
    }
}