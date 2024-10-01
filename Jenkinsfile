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
                    emailext(
                        to: "kaveen11111@gmail.com",
                        subject: "Security Scan Status Email",
                        body: "Security Scan was successful. Please find the logs attached.",
                       // Keep this for log attachment
                    )
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
                    emailext(
                        to: "kaveen11111@gmail.com",
                        subject: "Testing Status Email",
                        body: "The test was successful. Please find the logs attached.",
                 
                    )
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
