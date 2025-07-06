pipeline {
  agent any
  stages {
    stage('Checkout ') {
      steps {
        git(url: 'https://github.com/TheAmazingSui/JenkinsNewTest', branch: 'main', credentialsId: 'github-sui')
      }
    }

    stage('Build') {
      agent {
        docker {
          image 'node:18-alpine'
        }

      }
      steps {
        sh '''cd learn-jenkins-app
ls -la
node --version
npm --version
npm ci
npm run build'''
      }
    }

  }
}