pipeline {
    agent any
    stages {
        def build_result
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
                echo build_result
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
