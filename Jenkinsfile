pipeline {
  agent any
  stages {
    stage('Checkout ') {
      steps {
        git(url: 'https://github.com/TheAmazingSui/JenkinsNewTest', branch: 'main', credentialsId: 'github-sui')
      }
    }

    stage('Check npm') {
      steps {
        sh 'echo "without docker"'
      }
    }

  }
}