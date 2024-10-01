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
                echo 'Building the code...'
                // Add your build commands here
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Add your testing commands here
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

    post {
        success {
            emailext (
                to: "kaveen11111@gmail.com",
                subject: "Build Successful: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                body: "The build was successful!\n\nCheck the details at ${env.BUILD_URL}.",
                attachLog: true // Attach the log files
            )
        }
        failure {
            emailext (
                to: "kaveen11111@gmail.com",
                subject: "Build Failed: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                body: "The build failed.\n\nCheck the details at ${env.BUILD_URL}.",
                attachLog: true // Attach the log files
            )
        }
        unstable {
            emailext (
                to: "kaveen11111@gmail.com",
                subject: "Build Unstable: ${env.JOB_NAME} - Build #${env.BUILD_NUMBER}",
                body: "The build is unstable.\n\nCheck the details at ${env.BUILD_URL}.",
                attachLog: true // Attach the log files
            )
        }
    }
}
