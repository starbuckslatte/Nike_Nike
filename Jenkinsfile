pipeline {
  agent none
  stages {
    stage('Example Build') {
      steps {
        echo 'Hello World'
        build 'Nike_Build'
      }
    }

    stage('Example Deploy') {
      agent {
        label 'some-label'
      }
      when {
        beforeAgent true
        branch 'production'
      }
      steps {
        echo 'Deploying'
      }
    }

  }
}