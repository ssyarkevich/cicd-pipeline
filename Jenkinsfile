pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh '''chmod +x scripts/build.sh
./scripts/build.sh'''
      }
    }

    stage('Test') {
      steps {
        sh '''chmod +x scripts/test.sh
./scripts/test.sh'''
      }
    }

    stage('Build docker image') {
      steps {
        script {
          checkout scm
          def customImage = docker.build("${registry}:latest")
        }

      }
    }

    stage('Publish ') {
      steps {
        script {
          docker.withRegistry('', 'dockerhub-id'){
            docker.image("${registry}:latest").push('latest')
          }
        }

      }
    }

  }
  environment {
    registry = 'ssyarkevich/test-app'
  }
}