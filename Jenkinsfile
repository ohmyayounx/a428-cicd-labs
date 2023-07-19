node {
    agent {
        docker {
            image 'node:lts-buster-slim'
            args '-p 3000:3000'
        }
    }
    environment {
        CI = 'true'
    }
    stages ('Build') {
       sh 'npm install'   
    }
    stage ('Test') {
        sh './jenkins/scripts/test.sh'
    }
    stage ('Deploy'){
        sh './jenkins/scripts/deliver.sh'
        input message: 'Finished using the web site? (Click "Proceed" to continue)'
        sh './jenkins/scripts/kill.sh'
    }
}