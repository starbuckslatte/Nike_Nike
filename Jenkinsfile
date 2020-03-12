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

  }
}