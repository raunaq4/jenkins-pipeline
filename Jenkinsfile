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
                success {
                    mail to: 'aaaraunaq@gmail.com',
                    subject: 'Tests Status Email',
                    body: 'Tests were successful',
                    attachLog: true
                }
                failure {
                    mail to: 'aaaraunaq@gmail.com',
                    subject: 'Tests Status Email',
                    body: 'Tests failed',
                    attachLog: true
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
                success {
                    mail to: 'aaaraunaq@gmail.com',
                    subject: 'Secuity Scan Status Email',
                    body: 'Security Scan successful',
                    attachLog: true
                }
                failure {
                    mail to: 'aaaraunaq@gmail.com',
                    subject: 'Security Scan Status Email',
                    body: 'Security Scan failed',
                    attachLog: true
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
