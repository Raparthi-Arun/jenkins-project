pipeline {
    agent any
    stages {
        stage('Build Report') {
            steps {
                // Create "report" folder and sample index.html file
                bat 'mkdir report'
                writeFile file: 'report/index.html', text: '''
                <html>
                  <head><title>User Registration</title></head>
                  <body>
                    <h2>User Registration Form</h2>
                    <form>
                        <label for="name">Full Name:</label>
                        <input type="text" id="name" name="name" required><br><br>

                        <label for="email">Email:</label>
                        <input type="email" id="email" name="email" required><br><br>

                        <label for="phone">Phone Number:</label>
                        <input type="tel" id="phone" name="phone" required><br><br>

                        <label for="organisation">Organisation:</label>
                        <input type="text" id="organisation" name="organisation" required><br><br>

                        <input type="submit" value="Register">
                    </form>
                  </body>
                </html>
                '''
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
