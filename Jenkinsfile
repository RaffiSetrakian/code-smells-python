pipeline {
    environment {
        QODANA_TOKEN=credentials('qodana-token')
        QODANA_ENDPOINT='https://web.cloud.sssa-stgn.aws.intellij.net'
    }
    agent {
        docker {
            args '''
              -v "${WORKSPACE}":/data/project
              --entrypoint=""
              '''
            image 'jetbrains/qodana-python:2026.1'
        }
    }
    stages {
        stage('Qodana') {
            steps {
                sh '''qodana'''
            }
        }
    }
}
