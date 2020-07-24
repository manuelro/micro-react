pipeline {
  
  agent {
    docker {
      image 'alpine:3.11'
      args '-p 3000:3000'
    }
  }

  stages {
    
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
        sh 'npm build'
      }
    }

  }
}