pipeline{
    agent any

    environment {
        DIRECTORY_PATH="${env.PATH}"
        STAGING_ENVIRONMENT="AWS EC2 instance"
        PRODUCTION_ENVIRONMENT="AWS EC2 instance"
    }    


    stages{
        stage("Stage 1:Build"){
            steps{
                echo "Compiling and building code using Apache Mavern"
                echo "Mavern provides a platform for Java-based project to be built from source code of the project"
            } 
        }
        stage("Stage 2: Test"){
            steps{
                echo "Unit tests using JUnit"
                echo "JUnit is a testing framework for Java project, unit tests will test specific functions in source code"
                echo "Integration tests using Selenium"
                echo "Selenium will be used to test the functionaility of certain features of the application using automation"
            }
        }
        stage("Stage 3: Code Analysis"){
            steps{
                echo "Analysis code quality using Quality Monitor using Jenkins Warnings plugin"
                echo "The Quality Montitor feature from the Warnings plugin will monitor the tests, detected bugs and overall quality of the source code"
            }
        }
        stage("Stage 4: Security Scan"){
            steps{
                echo "Checking code for vulnerabilities using Snyk"
                echo "Snyk security scan will be performed to check any vulnerabilities in the source code"
            }
        }
        stage("Stage 5: Deploy to Staging"){
            steps{
                echo "Deploy the application to $STAGING_ENVIRONMENT"
                echo "Deploying to staging before production, this is so code can be further tested in an environment before deployed to production"
                echo "AWS EC2 instance will  be used for both the staging and production environments"
            }
        }
        stage("Stage 5: Integration Tests on Staging"){ 
            steps{
                echo "Running Integration test on $STAGING_ENVIRONMENT staging envrionment"
                echo "this will involve testing other third party services that interact with the software, catching potential bugs before deployed to prouduction"
            }
        }
        stage("Stage 7: Deploy to Production"){
            steps{
                echo "code from $DIRECTORY_PATH deployed successfully to $PRODUCTION_ENVIRONMENT"
                echo "code has succeeded previous steps, final stage is pushing to production"
            }
        }
    }
}