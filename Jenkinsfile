pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/Amellalzakaria/front_Blog_Jenkins.git', branch: 'master'
            }
        }

        stage('Install Dependencies') {
            steps {
                bat 'npm install' // Use 'bat' on Windows or 'sh' on Unix/Linux
            }
        }

        stage('Run Tests') {
            steps {
                bat 'npm test' // Use 'bat' on Windows or 'sh' on Unix/Linux
            }
        }

        stage('Build') {
            steps {
                bat 'npm run build' // Use 'bat' on Windows or 'sh' on Unix/Linux
                // Your build command might be different depending on your project setup
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying application...'
                // Add your deployment commands here
                // For example, you might use SCP, FTP, or other means to deploy the built assets
                // bat 'deploy-command' // Use 'bat' on Windows or 'sh' on Unix/Linux
            }
        }
    }

    post {
        always {
            echo 'Pipeline is complete.'
        }
        success {
            echo 'Success!'
        }
        failure {
            echo 'Failure!'
        }
    }
}
