pipeline{
    agent any
    environment {
        DIRECTORY_PATH="${env.PATH}"
        TESTING_ENVIRONMENT="SIT223"
        PRODUCTION_ENVIRONMENT="Jonathan Phillips"
    }
    stages{
        stage("Build"){
            steps{
                echo "Fetch the source code from $DIRECTORY_PATH"
                echo "Compile the code and generate any necessary artefacts"
            } 
        }
        stage("Test"){
            steps{
                echo "Unit tests"
                echo "Integration tests"
            }
        }
        stage("Code Quality Check"){
            steps{
                echo "Check the quality of the code"
            }
        }
        stage("Deploy"){
            steps{
                echo "Deploy the application to $TESTING_ENVIRONMENT"
            }
        }
        stage("Approval"){ 
            steps{
                script {
                    timeout(time: 15, unit: "SECONDS") {
                        echo "Waiting for approval"
                        sleep time: 10, unit: "SECONDS"
                        echo "Approved"
                    }
                }
            }
        }
        stage("Deploy to Production"){
            steps{
                echo "code from $DIRECTORY_PATH deployed successfully to $PRODUCTION_ENVIRONMENT"
            }
        }
    }
}