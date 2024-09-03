pipeline {
    agent any
    
    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the application...'
                    // Replace with your build commands if needed
                    sh 'echo "Build step completed"'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running Unit and Integration Tests...'
                    // Replace with your test commands if needed
                    sh 'echo "Tests completed"'
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Analyzing the code...'
                    // Replace with your code analysis commands if needed
                    sh 'echo "Code analysis completed"'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Scanning for security vulnerabilities...'
                    // Replace with your security scan commands if needed
                    sh 'echo "Security scan completed"'
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to Staging environment...'
                    // Replace with your deployment commands if needed
                    sh 'echo "Deployment to Staging completed"'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running Integration Tests on Staging...'
                    // Replace with your integration test commands if needed
                    sh 'echo "Integration tests on Staging completed"'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to Production...'
                    // Replace with your production deployment commands if needed
                    sh 'echo "Deployment to Production completed"'
                }
            }
        }
    }
    
    post {
        success {
            mail to: 'haritamang1115@gmail.com',
                subject: "Pipeline Successful",
                body: "The pipeline completed successfully."
        }
        failure {
            mail to: 'haritamang1115@gmail.com',
                subject: "Pipeline Failed",
                body: "The pipeline failed."
        }
    }
}
