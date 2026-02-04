pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/<your-username>/<your-repo>.git'
            }
        }

        stage('Compile') {
            steps {
                bat 'javac Hello.java'
            }
        }

        stage('Archive') {
            steps {
                archiveArtifacts artifacts: 'Hello.class', fingerprint: true
            }
        }
    }

    post {
        failure {
            error 'Build failed due to error'
        }
        success {
            echo 'CI Pipeline Successful'
        }
    }
}
