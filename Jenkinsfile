pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building the code using Maven"
            }
            emailext(
                to: "hongthamnguyen2703@gmail.com",
                subject: "Test Email",
                body: "This is a test email from Jenkins pipeline."
                )
        }
    }
}
