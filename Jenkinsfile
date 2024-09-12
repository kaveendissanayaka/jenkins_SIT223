pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the code...'
            }
            post {
                success {
                    mail to: "kaveen11111@gmail.com",
                    subject: "Build Status Email",
                    body: "The build was successful."
                }
            }
        }
    }
}

