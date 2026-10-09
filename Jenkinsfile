
pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo "Jenkins has checked out branch: ${env.BRANCH_NAME}"
            }
        }

        stage('Build') {
            steps {
                echo 'Checking project files...'
                bat 'dir'
            }
        }

        stage('Test') {
            steps {
                bat 'if exist Jenkinsfile (echo Jenkinsfile found) else (exit /b 1)'
            }
        }
    }

    post {
        success {
            echo 'Pipeline completed successfully!'
        }

        failure {
            echo 'Pipeline failed. Check the console output.'
        }
    }
}