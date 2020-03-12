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
                }
                echo "${currentBuild.result}"
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
