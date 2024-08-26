pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building the code using Maven."
            }
            post {
                success {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Build Stage Success",
                        body: "The Build stage has completed successfully!",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Build Stage Failure",
                        body: "The Build stage has failed!",
                        attachLog: true
                    )
                }
            }
        }

        stage("Unit and Integration Tests") {
            steps {
                echo "Running unit tests with JUnit and integration tests with Selenium."
            }
            post {
                success {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Unit and Integration Tests Success",
                        body: "The Unit and Integration Tests stage has completed successfully!",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Unit and Integration Tests Failure",
                        body: "The Unit and Integration Tests stage has failed!",
                        attachLog: true
                    )
                }
            }
        }

        stage("Code Analysis") {
            steps {
                echo "Analyzing code quality with SonarQube."
            }
        }

        stage("Security Scan") {
            steps {
                echo "Performing security scan using OWASP ZAP."
            }
            post {
                success {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Security Scan Success",
                        body: "The Security Scan stage has completed successfully!",
                        attachLog: true
                    )
                }
                failure {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Security Scan Failure",
                        body: "The Security Scan stage has failed!",
                        attachLog: true
                    )
                }
            }
        }

        stage("Deploy to Staging") {
            steps {
                echo "Deploying application to AWS EC2 staging server."
            }
        }

        stage("Integration Tests on Staging") {
            steps {
                echo "Running integration tests on staging environment using Selenium."
            }
        }

        stage("Deploy to Production") {
            steps {
                echo "Deploying application to AWS EC2 production server."
            }
        }
    }
}
