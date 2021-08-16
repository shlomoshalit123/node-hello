pipeline {
  agent {
    node {
      label 'Docker-slave'
    }

  }
  stages {
    stage('Checkout code') {
      steps {
        git(url: 'https://github.com/lidorg-dev/node-hello.git', branch: 'master', changelog: true, poll: true)
      }
    }

    stage('Build Docker Image') {
      steps {
        sh 'docker build . -t node-hello:$BUILD_ID'
      }
    }

    stage('Push Docker Image') {
      steps {
        sh '''# docker login 
# docker tag node-hello:$BUILD_ID lidorlg/node-hello:$BUILD_ID 
# && docker push lidorlg/node-hello:$BUILD_ID'''
      }
    }

  }
}