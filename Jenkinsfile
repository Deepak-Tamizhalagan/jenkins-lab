pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                echo 'Cloning the GitHub repository...'
                git branch: 'main', url: 'https://github.com/Deepak-Tamizhalagan/jenkins-lab.git', credentialsId: 'github-pat'
            }
        }

        stage('Build') {
            steps {
                echo '🧱 Building the project...'
                bat 'echo Build step simulation successful!'
            }
        }

        stage('Test') {
            steps {
                echo '🧪 Running tests...'
                bat 'echo Tests completed successfully!'
            }
        }
    }

    post {
        success {
            echo '✅ Build and test pipeline completed successfully!'
            emailext (
                subject: "✅ SUCCESS: Jenkins Build #${env.BUILD_NUMBER}",
                body: """<p>Good news!</p>
                        <p>Build <b>#${env.BUILD_NUMBER}</b> of job <b>${env.JOB_NAME}</b> completed successfully.</p>
                        <p><a href="${env.BUILD_URL}">Click here</a> to view build details.</p>""",
                mimeType: 'text/html',
                to: 'tamizhalagandeepak@gmail.com'
            )
        }

        failure {
            echo '❌ Build failed. Please check logs.'
            emailext (
                subject: "❌ FAILED: Jenkins Build #${env.BUILD_NUMBER}",
                body: """<p>Build <b>#${env.BUILD_NUMBER}</b> of job <b>${env.JOB_NAME}</b> has failed.</p>
                        <p>Check the build logs <a href="${env.BUILD_URL}">here</a>.</p>""",
                mimeType: 'text/html',
                to: 'tamizhalagandeepak@gmail.com'
            )
        }
    }
}
