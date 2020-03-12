def build_result
def stage_result
def uat_result
def deploy_result
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
            }
        }
        stage('Stage') {
            when {
                expression {
                    build_result == 'SUCCESS'
                }
            }
            steps {
                echo 'Stage mode'
                script {
                    try {
                        build job: 'StageProcess'
                        currentBuild.result = 'SUCCESS'
                    } catch (err) {
                        echo err
                        currentBuild.result = 'FAILURE'
                    }
                    stage_result = currentBuild.result
                    echo "Stage_result: ${stage_result}"
                }
            }
        }
        stage('UAT') {
            when {
                expression {
                    stage_result == 'SUCCESS'
                }
            }
            steps {
                echo 'UAT process'
                script {
                    try {
                        build job: 'UATProcess'
                        currentBuild.result = 'SUCCESS'
                    } catch (err) {
                        echo err
                        currentBuild.result = 'FAILURE'
                    }
                    uat_result = currentBuild.result
                    echo "uat_result: ${uat_result}"
                }
            }
        }
        stage('Deploy') {
            when {
                expression {
                    uat_result == 'SUCCESS'
                }
            }
            steps {
                echo 'Deploy process'
                script {
                    try {
                        build job: 'Route to Production'
                        currentBuild.result = 'SUCCESS'
                    } catch (err) {
                        echo err
                        currentBuild.result = 'FAILURE'
                    }
                    deploy_result = currentBuild.result
                    echo "uat_result: ${deploy_result}"
                }
            }
        }
    }
}