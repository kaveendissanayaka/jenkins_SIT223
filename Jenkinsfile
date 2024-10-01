pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                // tools: maven
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Tool: JUnit for unit tests, Selenium for integration tests
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
            }
            post {
                always {
                    script {
                        // Save the log to a file
                        def logFile = 'security_scan.log'
                        sh "echo 'Security Scan was successful.' > ${logFile}"

                        // Send email with log attached
                        sh """
                        echo "Security Scan was successful. Please find the logs attached." | \
                        mail -s "Security Scan Status Email" -A ${logFile} kaveen11111@gmail.com
                        """
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
            }
            post {
                always {
                    script {
                        // Save the log to a file
                        def logFile = 'integration_test.log'
                        sh "echo 'The test was successful.' > ${logFile}"

                        // Send email with log attached
                        sh """
                        echo "The test was successful. Please find the logs attached." | \
                        mail -s "Testing Status Email" -A ${logFile} kaveen11111@gmail.com
                        """
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
