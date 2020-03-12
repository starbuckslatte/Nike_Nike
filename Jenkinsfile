pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        build(job: 'Nike_Build', wait: true)
      }
    }

    stage('Stage') {
      steps {
        build 'StageProcess'
      }
    }

    stage('UAT') {
      steps {
        build 'UATProcess'
        error 'Build Fail'
      }
      post {
        success {
            echo 'I succeeeded!'
        }
        unstable {
            echo 'I am unstable :/'
        }
        failure {
            echo 'I failed :('
        }
      }
    }

    stage('Deployment') {
      steps {
        build 'Route to Production'
      }
    }

  }
}