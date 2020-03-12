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
          echo "Build result: ${build_result}"
        }
        stage('Deploy') {
            when {
                expression { build_result == 'SUCCESS' }
            }
            steps {
                echo 'Deploying'
            }

      }
    }

    stage('Deploy') {
      when {
        expression {
          build_result == 'FAILURE'
        }

      }
      steps {
        echo 'Deploying'
      }
    }

  }
}