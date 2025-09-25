pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                // Ensure folder exists
                bat 'mkdir report'
                // Copy HTML file into report folder
                bat 'copy index.html report\\index.html'
            }
        }

        stage('Publish Report') {
            steps {
                publishHTML([ 
                    reportDir: 'report',
                    reportFiles: 'index.html',
                    reportName: 'My Web Output',
                    keepAll: true,
                    alwaysLinkToLastBuild: true,
                    allowMissing: false
                ])
            }
        }
    }
}
