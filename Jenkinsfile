pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                script {
                    // Simulate a build log file
                    sh "echo 'Build successful.' > build.log"
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
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
                script {
                    // Simulate a security scan log file
                    sh "echo 'Security Scan was successful.' > security_scan.log"
                }
            }
            post {
                always {
                    script {
                        // Read log content for debugging
                        echo "Log content: ${readFile('security_scan.log')}"
                        
                        // Send email with log attached
                        emailext (
                            to: "kaveen11111@gmail.com",
                            subject: "Security Scan Status Email",
                            body: "Security Scan was successful.",
                            attachments: "security_scan.log"
                        )
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
                script {
                    // Simulate integration test log file
                    sh "echo 'Integration tests passed.' > integration_test.log"
                }
            }
            post {
                always {
                    script {
                        // Read log content for debugging
                        echo "Log content: ${readFile('integration_test.log')}"
                        
                        // Send email with log attached
                        emailext (
                            to: "kaveen11111@gmail.com",
                            subject: "Testing Status Email",
                            body: "The Test was successful.",
                            attachments: "integration_test.log"
                        )
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
            }
        }
    }
}
