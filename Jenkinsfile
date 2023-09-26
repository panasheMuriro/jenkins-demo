pipeline {
  agent any

  tools{
    nodejs: "20.7.0"
  }

  stages {
    stage('Checkout') {
      steps {
        checkout scm
      }
    }
    
    stage('Build') {
      steps {
        sh 'npm install'
      }
    }

    stage('Test') {
      steps {
        sh 'npm test'
      }
    }

    stage('Deploy') {
      steps {
        sh 'npm start &'
      }
    }
  }

  post {
    always {
      junit '**/test-*.xml'
    }
  }
}
