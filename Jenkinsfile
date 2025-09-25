pipeline {
  agent any 

  stages {
    stage('Checkout') {
        steps {
          git branch: 'main', url: 'https://github.com/nikolajovancevic-pixel/playwright-jenkins.git'        }
    }

    stage ('install playwright') {
      steps {
        sh '''
          npm i -D @playwright/test
          npx playwright install
        '''
      }
    }
    stage ('run test') {
      steps {
        sh '''
          npx playwright test
        '''
      }
    }
  }
  post {
      always {
          echo 'Build finished!'
      }
  }
}
