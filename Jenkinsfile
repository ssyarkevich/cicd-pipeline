pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        script {
          checkout scm
          def customImage = docker.build("${registry}:latest")
        }

      }
    }

    stage('Test') {
      steps {
        sh 'scripts/script.sh'
      }
    }

  }
  environment {
    registry = 'ssyarkevich/test-app'
  }
}