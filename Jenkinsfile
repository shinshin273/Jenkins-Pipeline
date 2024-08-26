pipeline {
    agent any
    stages {
        stage("Build") {
            steps {
                echo "Building the code using Maven"
            }
            post {
                always {
                    emailext(
                        to: "hongthamnguyen2703@gmail.com",
                        subject: "Build Stage Notification",
                        body: "This is a test email from Jenkins pipeline.",
                        attachLog: true
                    )
                }
            }
        }
    }
}
