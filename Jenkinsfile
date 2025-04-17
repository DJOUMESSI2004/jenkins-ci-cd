pipeline {
    agent any

    tools {
        nodejs 'Node-23-11-0'
    }

    environment {
        NEW_VERSION = '1.3.0'
        SERVER_CREDENTIALS = credentials('vm-ssh-key') // Jenkins credential ID
    }

    stages {
        stage('Build app') {
            steps {
                echo 'Building the app...'
                echo "App version: ${NEW_VERSION}"
                sh 'npm install'
                sh 'npm run build'
            }
        }

        stage('Test app') {
            steps {
                echo 'Running tests (if any)...'
            }
        }

        stage('Deploy app') {
            steps {
                echo 'Deploying the app to Windows VM...'

                sshagent(credentials: ['vm-ssh-key']) {
                    sh '''
                        echo "Sending build folder to Windows VM..."
                        scp -o StrictHostKeyChecking=no -r build/* 90502182@172.27.2.62:/c/ci-cd-server
                    '''
                }
            }
        }
    }

    post {
        always {
            // Add a step inside always to avoid the error
            echo 'Pipeline execution completed (whether success or failure).'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
