pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building the code using Maven"
            }
            post{
                success{
                    mail to: "hongthamnguyen2703@gmail.com",
                    subject: "Pipeline Success",
                    body: "The pipeline has completed successfully!",
                    attachLog: true
                }
                failure{
                    mail to: "hongthamnguyen2703@gmail.com",
                    subject: "Pipeline Failure",
                    body: "The pipeline has failed!",
                    attachLog: true
                }
            }
        }
        stage("Unit and Integration Tests"){
            steps{
                echo "Running unit tests with JUnit and integration tests with Selenium"
            }
        }

        stage("Code Analysis"){
            steps{
                echo "Analyzing code quality with SonarQube"
            }
        }

        stage("Security Scan"){
            steps{
                echo "Performing security scan using OWASP ZAP"
            }
        }

        stage("Deploy to Staging") {
            steps{
                echo "Deploying application to AWS EC2 staging server"
            }
        }

        stage("Integration Tests on Staging") {
            steps{
                echo "Running integration tests on staging environment using Selenium"
            }
        }

        stage("Deploy to Production"){
            steps{
                echo "Deploying application to AWS EC2 production server"
            }
        }
    }
}

