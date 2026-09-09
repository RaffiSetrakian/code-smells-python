pipeline {
    agent any
    environment {
        QODANA_TOKEN = credentials('qodana-token')
        QODANA_ENDPOINT = 'https://qodana.cloud'
    }
    stages {
        stage('Qodana') {
            steps {
                sh '/usr/local/bin/docker run --rm -v "${WORKSPACE}":/data/project --entrypoint="" -e QODANA_TOKEN=$QODANA_TOKEN -e QODANA_ENDPOINT=$QODANA_ENDPOINT jetbrains/qodana-python:2026.1 --show-report'
            }
        }
    }
}
