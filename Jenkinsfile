node {
    stage('Build') {
        checkout scm
        docker.image('node:6-alpine').inside('-d -p 80:3000') {
            sh 'yarn'
            sh 'yarn build'
        }
        def frontendImage = docker.build('a949690645/sentiment-analysis-frontend')
        sh 'docker login -u a949690645 -p a19950819'
        frontendImage.push()
    }
    stage('Deploy') {
        docker.withServer('tcp://106.14.220.125:2376') {
            docker.image('a949690645/sentiment-analysis-frontend').inside('-d -p 80:3000')
        }
    }
}
