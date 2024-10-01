pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // tools: maven
                script {
                    // Simulate a build log file
                    sh "echo 'Build successful.' > build.log"
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Tool: JUnit for unit tests, Selenium for integration tests
                script {
                    // Simulate a test log file
                    sh "echo 'Unit tests passed.' > test.log"
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code...'
                // Tool: SonarQube
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Tool: OWASP Dependency-Check
                script {
                    // Simulate a security scan log file
                    sh "echo 'Security Scan was successful.' > security_scan.log"
                }
            }
            post {
                always {
                    script {
                        // Send email with log attached
                        mail to: "kaveen11111@gmail.com",
                        subject: "Security Scan Status Email",
                        body: "Security Scan was successful.",
                        attach: "security_scan.log"
                    }
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Tool: AWS CLI or deployment scripts
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Tool: Similar tools as for Stage 2
                script {
                    // Simulate integration test log file
                    sh "echo 'Integration tests passed.' > integration_test.log"
                }
            }
            post {
                always {
                    script {
                        // Send email with log attached
                        mail to: "kaveen11111@gmail.com",
                        subject: "Testing Status Email",
                        body: "The Test was successful.",
                        attach: "integration_test.log"
                    }
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Tool: AWS CLI or deployment scripts
            }
        }
        stage('Complete process') {
            steps {
                echo 'Completed deployment to production...'
                // Tool: AWS CLI or deployment scripts
            }
        }
    }
}

// Configure SMTP in Jenkins
// Go to Manage Jenkins > Configure System and set up the following:
// E-mail Notification:
// SMTP server: smtp.your-email-provider.com
// Default user e-mail suffix: @your-email-provider.com
// Use SSL: true
// SMTP port: 465 (or 587 for TLS)
// Credentials: Add your email credentials here

// Extended E-mail Notification (for attachments):
// SMTP server: smtp.your-email-provider.com
// Default user e-mail suffix: @your-email-provider.com
// Use SSL: true
// SMTP port: 465 (or 587 for TLS)
// Credentials: Add your email credentials here
