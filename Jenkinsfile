pipeline {
  agent {
    docker {
      image mcr.microsoft.com/playwright:v1.55.0-noble
    }
  }
  stages {
    stage ('install playwright') {
      sh '''
        npm i -D @playwright/test
        npx playwright install
      '''
    }
    stage('test') {
      steps {
        sh '''
          npx playwright test --list
          npx playwright test
        '''
      }
    }
  }
}
