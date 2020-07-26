pipeline {
  
  agent {
    docker {
      image 'node:10.11.0-alpine'
      args '-p 3000:3000'
    }
  }

  environment {
    CI = 'true'
  }

  stages {

    stage('Config') {
      steps {
        sh 'npm config ls'
      }
    }
    
    stage('Install') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test:ci'
      }
    }

    stage('Build') {
      steps {
        sh 'npm run build'
      }
    }

    stage('Deliver') { 
        steps {
            sh './jenkins/scripts/deliver.sh' 
            input message: 'Finished using the web site? (Click "Proceed" to continue)' 
            sh './jenkins/scripts/kill.sh' 
        }
    }

  }
}