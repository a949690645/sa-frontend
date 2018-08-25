pipeline {
    agent none
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'node:6-alpine'
                    args '-d -p 80:3000'
                }
            }
            steps {
                sh 'yarn' 
                sh 'yarn start &'
            }
        }
    }
}
