pipeline {
    agent any
    stages {
        
        stage('Build app') {
            steps {
                echo 'the app is building.....!'
                sh 'yarn install'
                sh 'yarn run build'
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
}
