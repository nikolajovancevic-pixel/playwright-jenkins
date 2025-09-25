pipeline {
  agent any 

  stages {
    stage('Checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/nikolajovancevic-pixel/playwright-jenkins.git'        }
    }

    stage ('install playwright') {
      steps {
        bat 'npm ci'
        bat 'npx playwright install'
      }
    }
    stage ('run test') {
      steps {
          bat 'npx playwright test'
      }
    }
  }
  post {
      always {
          echo 'Build finished!'
      }
  }
}
