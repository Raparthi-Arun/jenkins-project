pipeline {
    agent any
    stages {
        stage('Build Report') {
            steps {
                // make sure report folder exists
                bat 'mkdir report'
                // copy index.html from workspace root (GitHub) to report folder
                bat 'copy index.html report\\index.html'
            }
        }
        stage('Publish Report') {
            steps {
                publishHTML([
                    reportDir: 'report',
                    reportFiles: 'index.html',
                    reportName: 'HTML Report',
                    keepAll: true,
                    alwaysLinkToLastBuild: true,
                    allowMissing: false
                ])
            }
        }
    }
}
