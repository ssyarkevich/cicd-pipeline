pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''chmod + x scripts/build.sh
./scripts/build.sh'''
      }
    }

  }
  environment {
    registry = 'ssyarkevich/test-app'
  }
}