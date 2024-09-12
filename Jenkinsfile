pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                //tools: maven
            }
            post {
                always {
                    mail to: "kaveen11111@gmail.com",
                    subject: "Build Status Email",
                    body: "The build was successful."
                }
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
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Tool: AWS CLI or deployment scripts
              
            }
        }
    }
}

