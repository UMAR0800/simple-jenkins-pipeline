pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                // Checkout code from GitHub
                git branch: 'main', url: 'https://github.com/umar0800/your-repo.git'
            }
        }

        stage('Install Dependencies') {
            steps {
                // Install Python dependencies
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Test') {
            steps {
                // Run tests using Python's unittest
                sh 'python -m unittest discover tests'
            }
        }

        stage('Deploy') {
            steps {
                // Deploy step - can be customized for your project
                echo 'Deploying the application...'
            }
        }
    }

    post {
        always {
            echo 'Cleaning up...'
            cleanWs() // Clean workspace after pipeline execution
        }
        success {
            echo 'Pipeline completed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
