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
        sh 'scripts/build.sh'
      }
    }

  }
  environment {
    registry = 'ssyarkevich/test-app'
  }
}