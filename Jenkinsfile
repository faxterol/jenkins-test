pipeline {
  agent any
  stages {
    stage('Pull') {
      steps {
        git(url: 'https://github.com/faxterol/jenkins-test', branch: '*/main')
      }
    }

    stage('Build') {
      steps {
        sh 'mvn install'
      }
    }

    stage('Finish') {
      steps {
        validateDeclarativePipeline './dist/*.jar'
      }
    }

  }
  environment {
    ENVIRONMENT = 'DEVTEST'
  }
}