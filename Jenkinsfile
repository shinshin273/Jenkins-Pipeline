pipeline {
    agent any

    environment {
        DIRECTORY_PATH = 'C:\\Users\\hongt\\Desktop\\DEAKIN\\Tri 2\\SIT753\\Week 6'
        TESTING_ENVIRONMENT = 'testing'
        PRODUCTION_ENVIRONMENT = 'Shin'
        RECIPIENT_EMAIL = 'hongthamnguyen2703@gmail.com'  // Replace with the actual email address
    }

    stages {
        stage('Build') {
            steps {
                echo "Fetching the source code from: ${env.DIRECTORY_PATH}"
                echo "Compiling the code and generating necessary artifacts using Maven"
                // Example command: sh 'mvn clean package'
            }
        }

        stage('Unit and Integration Tests') {
            steps {
                echo "Running unit tests with JUnit"
                echo "Running integration tests"
                // Example command: sh 'mvn test'
            }
            post {
                always {
                    emailext (
                        to: "${env.RECIPIENT_EMAIL}",
                        subject: "Jenkins Pipeline - Unit and Integration Tests Status: ${currentBuild.currentResult}",
                        body: "The Unit and Integration Tests stage has completed with status: ${currentBuild.currentResult}.",
                        attachLog: true
                    )
                }
            }
        }

        stage('Code Analysis') {
            steps {
                echo "Performing code quality analysis using SonarQube"
                // Example command: sh 'sonar-scanner'
            }
        }

        stage('Security Scan') {
            steps {
                echo "Performing security scan using OWASP Dependency Check"
                // Example command: sh 'dependency-check.sh --project test --scan /path/to/code'
            }
            post {
                always {
                    emailext (
                        to: "${env.RECIPIENT_EMAIL}",
                        subject: "Jenkins Pipeline - Security Scan Status: ${currentBuild.currentResult}",
                        body: "The Security Scan stage has completed with status: ${currentBuild.currentResult}.",
                        attachLog: true
                    )
                }
            }
        }

        stage('Deploy to Staging') {
            steps {
                echo "Deploying application to the staging environment: ${env.TESTING_ENVIRONMENT} (e.g., AWS EC2)"
                // Example command: sh 'scp target/app.jar ec2-user@staging-server:/path/to/deploy'
            }
        }

        stage('Integration Tests on Staging') {
            steps {
                echo "Running integration tests on the staging environment"
                // Example command: sh 'mvn verify -Pstaging'
            }
        }

        stage('Deploy to Production') {
            steps {
                echo "Deploying application to the production environment: ${env.PRODUCTION_ENVIRONMENT} (e.g., AWS EC2)"
                // Example command: sh 'scp target/app.jar ec2-user@production-server:/path/to/deploy'
            }
        }
    }
}
