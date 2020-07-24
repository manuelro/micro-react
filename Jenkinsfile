pipeline {
  agent {
    docker {
      image 'alpine:3.11'
      args '-p 3000:3000'
    }
  }
  stages {
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }
  }
}