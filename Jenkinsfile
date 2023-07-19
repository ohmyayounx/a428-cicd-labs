node {
    stage('Build') {
        // Set up the virtual environment and install dependencies
        sh './jenkins/script/build.sh'
    }
    
    stage('Test') {
        // Run tests
        sh './jenkins/scripts/test.sh'
    }
    
    stage('Deliver') {
        // Package the project for delivery (e.g., create a distribution package)
        sh './jenkins/scripts/deliver.sh'
        input message: 'Finished using the web site? (Click "Proceed" to continue)'
        sh './jenkins/scripts/kill.sh'
        
        // Perform any additional steps for delivery (e.g., deploy to a server)
        // ...
    }
    }
