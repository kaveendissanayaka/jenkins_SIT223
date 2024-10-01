pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
            }
            post {
                always {
                    script {
                        def logFile = 'security_scan.log'
                        sh "echo 'Security Scan was successful.' > ${logFile}"

                        // Use the emailext function to send email with attachment
                        emailext(
                            to: "kaveen11111@gmail.com",
                            subject: "Security Scan Status Email",
                            body: "Security Scan was successful. Please find the logs attached.",
                            attachLog: true,
                            attachmentsPattern: "${logFile}"
                        )
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
            }
            post {
                always {
                    script {
                        def logFile = 'integration_test.log'
                        sh "echo 'The test was successful.' > ${logFile}";

                        // Use the emailext function to send email with attachment
                        emailext(
                            to: "kaveen11111@gmail.com",
                            subject: "Testing Status Email",
                            body: "The test was successful. Please find the logs attached.",
                            attachLog: true,
                            attachmentsPattern: "${logFile}"
                        )
                    }
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
            }
        }
        stage('Complete process') {
            steps {
                echo 'Completed deployment to production...'
            }
        }
    }
}
