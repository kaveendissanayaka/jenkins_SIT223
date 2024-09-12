pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
            post {
                always {
                    mail to: "kaveen11111@gmail.com",
                    subject: "Build Status Email",
                    body: "The build was successful."
                }
            }
        }
        stage('Test') {
            steps {
                echo 'Testing the code...'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying the code...'
            }
        }
    }
}

