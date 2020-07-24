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

    stage('NPM Config') {
      steps {
        sh 'npm config ls'
      }
    }
    
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm run test:ci'
      }
    }

    stage('CRA Build') {
      steps {
        sh 'npm run build'
      }
    }

  }
}