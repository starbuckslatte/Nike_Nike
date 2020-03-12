pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Hello World'
                def jobResult = jobBuild.getResult()
                echo "Returned result: ${jobResult}"
                if (jobResult != 'SUCCESS') {
                    error("testJob failed with result: ${jobResult}")
                }

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
}