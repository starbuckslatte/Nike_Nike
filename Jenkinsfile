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
      agent {
        label 'some-label'
      }
      when {
        build_result "Success"
        branch 'production'
      }
      steps {
        echo 'Deploying'
      }
    }

  }
}