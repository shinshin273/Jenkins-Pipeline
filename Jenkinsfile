pipeline{
    agent any
    stages{
        stage("Build"){
            steps{
                echo "Building..."
            }
            post{
                success{
                    mail to: "hongthamnguyen2703@gmail.com",
                    subject: "Build Status Email",
                    body: "Build was successful!"
                }
            }
        }
    }
}