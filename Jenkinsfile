pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
        script {
          try {
            build job: 'Nike_Build'
          } catch (err) {
            echo err
          }
        }

        echo currentBuild.result
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