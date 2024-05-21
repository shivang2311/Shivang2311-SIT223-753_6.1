pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                script {
                    echo 'Building the code...'
                    // Specify build tool, e.g., Maven
                    echo 'Tool: Maven'
                }
            }
        }
        stage('Unit and Integration Tests') {
            steps {
                script {
                    echo 'Running Unit and Integration Tests...'
                    // Specify test automation tools, e.g., JUnit for unit tests, TestNG for integration tests
                    echo 'Tools: JUnit, TestNG'
                }
            }
            post {
                always {
                    emailext (
                        to: 'rathishivang5556@gmail.com',
                        subject: "Unit and Integration Tests Stage: ${currentBuild.fullDisplayName}",
                        body: "The Unit and Integration Tests stage has completed with status: ${currentBuild.currentResult}.",
                        attachmentsPattern: '**/target/*.log'
                    )
                }
            }
        }
        stage('Code Analysis') {
            steps {
                script {
                    echo 'Performing Code Analysis...'
                    // Specify code analysis tool, e.g., SonarQube
                    echo 'Tool: SonarQube'
                }
            }
        }
        stage('Security Scan') {
            steps {
                script {
                    echo 'Performing Security Scan...'
                    // Specify security scan tool, e.g., OWASP Dependency Check
                    echo 'Tool: OWASP Dependency Check'
                }
            }
            post {
                always {
                    emailext (
                        to: 'rathishivang5556@gmail.com',
                        subject: "Security Scan Stage: ${currentBuild.fullDisplayName}",
                        body: "The Security Scan stage has completed with status: ${currentBuild.currentResult}.",
                        attachmentsPattern: '**/target/*.log'
                    )
                }
            }
        }
        stage('Deploy to Staging') {
            steps {
                script {
                    echo 'Deploying to Staging...'
                    // Specify deployment method, e.g., AWS CLI
                    echo 'Tool: AWS CLI'
                }
            }
        }
        stage('Integration Tests on Staging') {
            steps {
                script {
                    echo 'Running Integration Tests on Staging...'
                    // Specify testing tool, e.g., Selenium
                    echo 'Tool: Selenium'
                }
            }
        }
        stage('Deploy to Production') {
            steps {
                script {
                    echo 'Deploying to Production...'
                    // Specify deployment method, e.g., AWS CLI
                    echo 'Tool: AWS CLI'
                }
            }
        }
    }

    post {
        always {
            script {
                echo 'Sending Final Notification Email...'
                // Final email notification for overall pipeline result
                emailext (
                    to: 'rathishivang5556@gmail.com',
                    subject: "Pipeline ${currentBuild.fullDisplayName} - ${currentBuild.currentResult}",
                    body: "Pipeline ${currentBuild.fullDisplayName} finished with status: ${currentBuild.currentResult}.",
                    attachmentsPattern: '**/target/*.log'
                )
            }
        }
    }
}
