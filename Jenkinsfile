pipeline {
    agent any
    stages {
        stage('Build Report') {
            steps {
                // create a test HTML file
                sh 'mkdir -p report'
                writeFile file: 'report/index.html', text: '<html><body><h2>Hello Jenkins Report!</h2></body></html>'
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
