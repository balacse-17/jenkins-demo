pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Source code checked out from GitHub'
            }
        }

        stage('Test') {
            steps {
                bat 'if exist index.html (echo HTML file exists - Test passed) else (echo HTML file missing & exit /b 1)'
            }
        }

        stage('Build') {
            steps {
                bat 'if not exist build mkdir build'
                bat 'copy /Y index.html build\\index.html'
                echo 'Build completed successfully'
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying HTML application...'
                echo 'HTML application deployed successfully!'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}