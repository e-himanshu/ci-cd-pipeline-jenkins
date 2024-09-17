pipeline {
    agent any

    environment {
        EMAIL_FROM = 'bhattaraihimanshu426@gmail.com'
        EMAIL_TO = 'bhattaraihimanshu426@gmail.com'
        EMAIL_SUBJECT_SUCCESS = 'Pipeline Successful'
        EMAIL_SUBJECT_FAILURE = 'Pipeline Failed'
    }

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/e-himanshu/ci-cd-pipeline-jenkins.git', branch: 'main'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Checkout - ${currentBuild.currentResult}",
                        body: "The Checkout stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Build') {
            steps {
                echo 'Now Building the application...'
                sh 'echo Build step completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Build - ${currentBuild.currentResult}",
                        body: "The Build stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running Unit and Integration Tests...'
                sh 'echo Tests completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Unit and Integration Tests - ${currentBuild.currentResult}",
                        body: "The Unit and Integration Tests stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing the code...'
                sh 'echo Code analysis completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Code Analysis - ${currentBuild.currentResult}",
                        body: "The Code Analysis stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Scanning for security vulnerabilities...'
                sh 'echo Security scan completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Security Scan - ${currentBuild.currentResult}",
                        body: "The Security Scan stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to Staging environment...'
                sh 'echo Deployment to Staging completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Deploy to Staging - ${currentBuild.currentResult}",
                        body: "The Deploy to Staging stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running Integration Tests on Staging...'
                sh 'echo Integration tests on Staging completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Integration Tests on Staging - ${currentBuild.currentResult}",
                        body: "The Integration Tests on Staging stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to Production...'
                sh 'echo Deployment to Production completed'
                script {
                    emailext(
                        to: EMAIL_TO,
                        subject: "Stage: Deploy to Production - ${currentBuild.currentResult}",
                        body: "The Deploy to Production stage has ${currentBuild.currentResult}.",
                        from: EMAIL_FROM
                    )
                }
            }
        }
    }
    post {
        always {
            emailext(
                to: EMAIL_TO,
                subject: "Pipeline Summary - ${currentBuild.currentResult}",
                body: "The Jenkins pipeline has ${currentBuild.currentResult}. Check the logs for details.",
                from: EMAIL_FROM
            )
        }
    }
}
