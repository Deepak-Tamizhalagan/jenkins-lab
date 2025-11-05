pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the GitHub repository...'
                git branch: 'main',
                    credentialsId: 'github-pat',
                    url: 'https://github.com/Deepak-Tamizhhalagan/jenkins-lab.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the application...'
                // Simulate build
                sh 'echo "Build successful!"'
            }
        }

        stage('Test') {
            steps {
                echo 'Running tests...'
                sh 'echo "All tests passed successfully!"'
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
