pipeline {
    agent any

    tools {
        jdk 'JDK 8'
        gradle 'Gradle 8.4'
    }

    stages {
        stage('Build'){
        echo 'Building Code'
        sh './gradlew build'
        }
        stage('Test') {
            steps {
                echo 'Testing JUnit'
                sh './gradlew test'
            }
            post {
                always{
                    junit 'build/test-results/**/*.xml'
                }
            }
        }
    }
}