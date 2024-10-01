pipeline {
    agent any

    stages {
        stage('Checkout SCM') {
            steps {
                checkout scm
            }
        }
        stage('Build') {
            steps {
                echo 'Building the codes...'
                // Add your build commands here
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Add your testing commands here
            }
            post {
                success {
                    emailext (
                        to: "kaveen11111@gmail.com",
                        subject: "Unit and Integration Tests Successful: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                        body: "The unit and integration tests were successful!.",
                        attachLog: true // Attach the log files
                    )
                }
                failure {
                    emailext (
                        to: "kaveen11111@gmail.com",
                        subject: "Unit and Integration Tests Failed: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                        body: "The unit and integration tests failed..",
                        attachLog: true // Attach the log files
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                // Add your code analysis commands here
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Add your security scan commands here
            }
            post {
                success {
                    emailext (
                        to: "kaveen11111@gmail.com",
                        subject: "Security Scan Successful: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                        body: "The security scan was successful!.",
                        attachLog: true // Attach the log files
                    )
                }
                failure {
                    emailext (
                        to: "kaveen11111@gmail.com",
                        subject: "Security Scan Failed: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                        body: "The security scan failed.",
                        attachLog: true // Attach the log files
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Add your deployment commands here
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Add your integration testing commands here
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Add your production deployment commands here
            }
        }
    }

   
}
