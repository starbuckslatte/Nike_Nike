pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Hello World'
                def myjob = build job: 'Nike_Build'
                def result = myjob.getResult();
                // echo "${myjob.getResult()}"
                // if (${myjob.getResult()} != 'SUCCESS') {
                //     error("testJob failed with result: ${myjob.getResult()}")
                // }
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
