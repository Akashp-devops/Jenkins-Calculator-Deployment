pipeline {
    agent any

    environment {
        APP_NAME = 'calculator-app'
        DEPLOY_DIR = '/var/www/html/calculator'
        SERVER = 'ubuntu@13.61.187.188'  // Updated with your server's IP and username
    }

    stages {
        stage('Checkout') {
            steps {
                git 'https://github.com/Akashp-devops/Jenkins-Calculator-Deployment.git'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Add any build steps here, if applicable
                    echo 'Building the app...'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Add your test scripts or steps here
                    echo 'Running tests...'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Deployment steps (SCP, SSH, or any other deployment method)
                    echo "Deploying ${APP_NAME} to ${DEPLOY_DIR}"
                    sh 'scp -r ./* ubuntu@13.61.187.188:/var/www/html/calculator/'  // Updated with correct server IP and username
                }
            }
        }

        stage('Clean Up') {
            steps {
                script {
                    // Clean-up steps (if necessary)
                    echo 'Cleaning up...'
                }
            }
        }
    }

    post {
        always {
            echo 'Pipeline finished.'
        }
        success {
            echo 'Deployment was successful!'
        }
        failure {
            echo 'Deployment failed. Please check logs.'
        }
    }
}
