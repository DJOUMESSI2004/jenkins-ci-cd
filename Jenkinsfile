pipeline {
    agent any
    stages {
        
        stage('Build app') {
            steps {
                echo 'the app is building.....!'
                nodejs('Node-23-11-0'){
                    sh 'yarn install'
                    sh 'yarn build'
                }
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
