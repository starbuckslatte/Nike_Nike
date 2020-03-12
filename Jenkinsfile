pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
        catchError(message: 'Result')
      }
    }

    stage('Example Deploy') {
      when {
        branch 'production'
      }
      steps {
        echo 'Deploying'
      }
    }

  }
}