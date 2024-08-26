pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building the code using Maven"
            }
        }

        stage("Unit and Integration Tests") {
            steps {
                echo "Running unit tests with JUnit and integration tests with Selenium"
            }
            post {
                success {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Pipeline Success: Unit and Integration Tests",
                        body: "The Unit and Integration Tests stage has completed successfully.",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Pipeline Failure: Unit and Integration Tests",
                        body: "The Unit and Integration Tests stage has failed.",
                        attachLog: true
                    )
                }
            }
        }

        stage("Code Analysis") {
            steps {
                echo "Analyzing code quality with SonarQube"
            }
        }

        stage("Security Scan") {
            steps {
                echo "Performing security scan using OWASP ZAP"
            }
            post {
                success {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Pipeline Success: Security Scan",
                        body: "The Security Scan stage has completed successfully.",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Pipeline Failure: Security Scan",
                        body: "The Security Scan stage has failed.",
                        attachLog: true
                    )
                }
            }
        }

        stage("Deploy to Staging") {
            steps {
                echo "Deploying application to AWS EC2 staging server"
            }
        }

        stage("Integration Tests on Staging") {
            steps {
                echo "Running integration tests on staging environment using Selenium"
            }
        }

        stage("Deploy to Production") {
            steps {
                echo "Deploying application to AWS EC2 production server"
            }
        }
    }
}
