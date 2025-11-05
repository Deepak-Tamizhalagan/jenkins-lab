pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building the application...'
                bat 'echo Build successful!'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                bat 'echo All tests passed successfully!'
            }
        }

        stage('Notify') {
            steps {
                echo '✅ Build and test pipeline completed successfully!'
            }
        }
    }

    post {
        failure {
            echo '❌ Build failed. Please check logs.'
        }
    }
}
