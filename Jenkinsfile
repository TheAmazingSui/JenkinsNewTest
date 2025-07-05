pipeline {
  agent any
  stages {
    stage('Checkout ') {
      steps {
        git(url: 'https://github.com/TheAmazingSui/JenkinsNewTest', branch: 'main', credentialsId: 'github-sui')
      }
    }

    stage('Check npm') {
      parallel {
        stage('w/o docker') {
          steps {
            sh 'echo "without docker"'
            sh 'ls -la'
            sh 'touch container-no.txt'
          }
        }

        stage('with docker') {
          agent {
            docker {
              image 'node:18-alpine'
            }

          }
          steps {
            sh 'echo "With Docker"'
            sh 'ls -la'
            sh 'touch container-yes.txt'
            sh 'npm --version'
          }
        }

      }
    }

  }
}