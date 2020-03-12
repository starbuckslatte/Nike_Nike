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

                stage('Deploy') {
                    when {
                        build_result 'production'
                    }
                    steps {
                        echo 'Deploying'
                    }
                }
            }
        }
    }
}