pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
        build 'Nike_Build'
      }
      post {
          success {
              build_result: 'Success',
          }
          failure {
              build_result: 'Failure',
          }
      }

    }

    stage('Stage') {
      when {
        build_result: 'Success'
      }
      steps {
        echo 'Deploying'
      }
    }

  }
}