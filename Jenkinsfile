pipeline {
  agent none
  parameters {
      string(build_result: '')
  }
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
      steps {
        echo 'Deploying'
      }
    }

  }
}