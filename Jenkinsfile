pipeline { 
    agent any
    stages {

        stage('Build') {
            steps {
                echo 'compile and package code'
                echo 'automate the build using Maven'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo 'unit tests'
                echo 'run unit tests using JUnit'
                echo 'integration tests'
                echo 'run integration tests using TestNG'
            }
            post {
                always {
                    emailext (
                        to: 'aaaraunaq@gmail.com',
                        subject: "Jenkins Build: ${currentBuild.fullDisplayName}",
                        body: """<p>Stage 'Unit and Integration Tests' completed with status ${currentBuild.result}</p>
                            <p>Check console output at ${env.BUILD_URL} to view the results.</p>""",
                        attachLog: true
                    ) 
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo 'analyse the code and ensure it meets industry standards using SonarQube'
            }
        }

        stage('Secuity Scan') {
            steps {
                echo 'perform security scan on the code using OWASP ZAP to identify any vulnerabilities'
            }
            post {
                always {
                    emailext (
                        to: 'aaaraunaq@gmail.com',
                        subject: "Jenkins Build: ${currentBuild.fullDisplayName}",
                        body: """<p>Stage 'Security Scan' completed with status ${currentBuild.result}</p>
                            <p>Check console output at ${env.BUILD_URL} to view the results.</p>""",
                        attachLog: true
                    ) 
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo 'deployed the application to an AWS EC2 staging server'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo 'run integration tests on the staging environment'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo 'Deployed to AWS EC2 production server'
            }
        }
    }
}
