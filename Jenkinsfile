pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
                script {
                    sh "echo 'Build successful.' > build.log"
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                script {
                    sh "echo 'Unit tests passed.' > test.log"
                }
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
                script {
                    sh "echo 'Security Scan was successful.' > security_scan.log"
                }
            }
            post {
                always {
                    script {
                        echo "Log content: ${readFile('security_scan.log')}"
                        emailext (
                            to: "kaveen11111@gmail.com",
                            subject: "Security Scan Status Email",
                            body: "Security Scan was successful.",
                            attachments: "${env.WORKSPACE}/security_scan.log",
                            mimeType: 'text/plain'
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
                script {
                    sh "echo 'Integration tests passed.' > integration_test.log"
                }
            }
            post {
                always {
                    script {
                        echo "Log content: ${readFile('integration_test.log')}"
                        emailext (
                            to: "kaveen11111@gmail.com",
                            subject: "Testing Status Email",
                            body: "The Test was successful.",
                            attachments: "${env.WORKSPACE}/integration_test.log",
                            mimeType: 'text/plain'
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
