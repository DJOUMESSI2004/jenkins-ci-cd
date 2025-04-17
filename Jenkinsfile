pipeline {
    agent any

    tools {
        nodejs 'Node-23-11-0'
    }
    stages {
        
        stage('Build app') {
            steps {
                echo 'the app is building.....!'
                sh 'npm install'
                sh 'npm run build'
            }
        }

         stage('Test app') {
            steps {
                echo 'Testing the application......'
            }
        }


         stage('Deploy app') {
            steps {
                echo 'Deploy the application .....'
            }
        }
    }

    post {
        always{
            
        }
    }
}
