pipeline {
    agent any
    environment {
        QODANA_TOKEN = credentials('qodana-token')
        QODANA_ENDPOINT = 'https://web.cloud.sssa-stgn.aws.intellij.net'
    }
    stages {
        stage('Qodana') {
            steps {
                sh 'docker run --rm -v "${WORKSPACE}":/data/project -e QODANA_TOKEN=$QODANA_TOKEN -e QODANA_ENDPOINT=$QODANA_ENDPOINT jetbrains/qodana-python:2026.1 --show-report'
            }
        }
    }
}
