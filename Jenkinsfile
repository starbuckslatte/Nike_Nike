pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        echo 'Build Process'
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
        echo "Build Result2: ${build_result}"
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