pipeline {
    agent none
    stages {
        stage('Build') { 
            agent {
                docker {
                    image 'node:6-alpine'
                    args '-p 80:80'
                }
            }
            steps {
                sh 'yarn' 
                sh 'yarn start &'
            }
        }
    }
}
