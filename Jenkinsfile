pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Get code from GitHub repository
                git credentialsId: 'LeeJinCICD', url: 'https://github.com/dkwktm45/test-chaza.git'
            }
        }
        stage('Build') {
            steps {
                // Build and package the Spring project using Gradle
                sh './gradlew clean build -x test'
            }
        }
        stage('Archive') {
            steps {
                // Archive the built JAR file as an artifact
                archiveArtifacts artifacts: '**/build/libs/*.jar', allowEmptyArchive: true
            }
        }
    }
}