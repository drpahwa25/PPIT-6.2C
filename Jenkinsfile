pipeline {
 agent any

 environment {
 DIRECTORY_PATH = "/path/to/code/directory"
 TESTING_ENVIRONMENT = "TestingEnv"
 PRODUCTION_ENVIRONMENT = "YourNameProdEnv"
 }

 stages {
 stage('Build') {
 steps {
 echo "Fetching the source code from the directory path:
 ${env.DIRECTORY_PATH}"
 echo "Compiling the code and generating artifacts"
 }
 }

 stage('Test') {
 steps {
 echo "Running unit tests"
 echo "Running integration tests"
 }
 post {

                success {

                    mail to: "drpahwa25@gmail.com",

                    subject: "Test success",

                    body: "Test Success"

                }

   

            }
 }

 stage('Code Quality Check') {
 steps {
    7 echo "Checking the quality of the code"
 }
 }

 stage('Deploy') {
 steps {
 echo "Deploying the application to ${env.TESTING_ENVIRONMENT}"
 }
 }

 stage('Approval') {
 steps {
 echo "Waiting for manual approval..."
 sleep 10
 }
 }

 stage('Deploy to Production') {
 steps {
 echo "Deploying the code to the production environment: ${env.PRODUCTION_ENVIRONMENT}"
 }
 }
 }

 post {
    success {
 echo "Pipeline executed successfully"
 }
 failure {
 echo "Pipeline execution failed"
 }
 }
 }