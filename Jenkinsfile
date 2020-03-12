pipeline {
  agent none
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
        build 'Nike_Build'
      }
    }

    stage('Stage') {
      when {
        build_result 'Success'
      }
      steps {
        echo 'Deploying'
      }
    }

  }
}