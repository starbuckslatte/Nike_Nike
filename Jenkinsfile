pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Hello World'
        script {
          try {
            build job: 'Nike_Build'
            currentBuild.result = 'SUCCESS'
          } catch (err) {
            echo err
            currentBuild.result = 'FAILURE'
          }
          build_result = currentBuild.result
        }

        echo "Build Result: ${currentBuild.result}"
      }
    }

    stage('Deploy') {
      when {
        branch 'production'
      }
      steps {
        echo 'Deploying'
      }
    }

  }
}