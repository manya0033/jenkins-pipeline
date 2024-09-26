pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                echo 'Building the project...'
                // Example build tool: Maven
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                echo 'Running unit and integration tests...'
                // Example test tool: JUnit
                script {
                    currentBuild.result = 'SUCCESS'
                    emailext(
                        to: 'manyamahajan3003@gmail.com',
                        subject: "Build ${currentBuild.fullDisplayName} - Unit and Integration Tests",
                        body: """<p>The Unit and Integration Tests stage has completed with status: ${currentBuild.result}.</p>""",
                        attachLog: true
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                echo 'Analyzing code quality...'
                // Example analysis tool: SonarQube
            }
        }
        stage('Security Scan') {
            steps {
                echo 'Performing security scan...'
                // Example security tool: OWASP Dependency-Check
                script {
                    currentBuild.result = 'SUCCESS'
                    emailext(
                        to: 'manyamahajan3003@gmail.com',
                        subject: "Build ${currentBuild.fullDisplayName} - Security Scan",
                        body: """<p>The Security Scan stage has completed with status: ${currentBuild.result}.</p>""",
                        attachLog: true
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                echo 'Deploying to staging...'
                // Example deployment tool: AWS CLI
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                echo 'Running integration tests on staging...'
                // Example test tool: Selenium
            }
        }
        stage('Deploy to Production') {
            steps {
                echo 'Deploying to production...'
                // Example deployment tool: AWS CLI
            }
        }
    }
    post {
        success {
            script {
                emailext(
                    to: 'manyamahajan3003@gmail.com',
                    subject: "Jenkins Build Successful",
                    body: "The build was successful.",
                    attachLog: true
                )
            }
        }
        failure {
            script {
                emailext(
                    to: 'manyamahajan3003@gmail.com',
                    subject: "Jenkins Build Failed",
                    body: "The build failed.",
                    attachLog: true
                )
            }
        }
    }
}

