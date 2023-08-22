pipeline {
    agent any

    stages {

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