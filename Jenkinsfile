pipeline {
    agent any

    environment {
        SMTP_SERVER = 'smtp.gmail.com'
        SMTP_PORT = '587'
        EMAIL_FROM = 'bhattaraihimanshu426@gmail.com'
        EMAIL_TO = 'haritamang1115@gmail.com'
        EMAIL_SUBJECT_SUCCESS = 'Pipeline Successful'
        EMAIL_SUBJECT_FAILURE = 'Pipeline Failed'
        // Assuming you have added your credentials in Jenkins credentials manager
        EMAIL_CREDENTIALS_ID = 'qjul xnkj jhyu zmar' // Replace with your Jenkins credentials ID
    }

    stages {
        stage('Checkout') {
            steps {
                checkout([$class: 'GitSCM', 
                          userRemoteConfigs: [[url: 'https://github.com/e-himanshu/ci-cd-pipeline-jenkins.git']]])
            }
        }
        stage('Build') {
            steps {
                echo 'Building the application...'
                sh 'echo Build step completed'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                sh 'echo Tests completed'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code...'
                sh 'echo Code analysis completed'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for security vulnerabilities...'
                sh 'echo Security scan completed'
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
                sh 'echo Deployment to Staging completed'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                sh 'echo Integration tests on Staging completed'
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                sh 'echo Deployment to Production completed'
            }
        }
    }
    post {
        success {
            script {
                def mailCredentials = credentials(EMAIL_CREDENTIALS_ID)
                emailext(
                    to: EMAIL_TO,
                    subject: EMAIL_SUBJECT_SUCCESS,
                    body: 'The Jenkins pipeline has completed successfully.',
                    smtpServer: SMTP_SERVER,
                    smtpPort: SMTP_PORT,
                    smtpUsername: mailCredentials.username,
                    smtpPassword: mailCredentials.password
                )
            }
        }
        failure {
            script {
                def mailCredentials = credentials(EMAIL_CREDENTIALS_ID)
                emailext(
                    to: EMAIL_TO,
                    subject: EMAIL_SUBJECT_FAILURE,
                    body: 'The Jenkins pipeline has failed. Please check the logs for details.',
                    smtpServer: SMTP_SERVER,
                    smtpPort: SMTP_PORT,
                    smtpUsername: mailCredentials.username,
                    smtpPassword: mailCredentials.password
                )
            }
        }
    }
}
