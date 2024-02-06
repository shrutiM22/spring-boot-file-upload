pipeline {
    agent any
    
    stages {
        stage('Checkout') {
            steps {
                // Checkout source code from version control
                script {
                    checkout scm
                }
            }
        }
        
        stage('Build') {
            steps {
                // Build Spring Boot application
                script {
                    sh './mvnw clean install'
                }
            }
        }
        
        stage('Test') {
            steps {
                // Run tests
                script {
                    sh './mvnw test'
                }
            }
        }
    }
    
    post {
        always {
            // Clean up (optional)
            deleteDir()
        }
    }
}
