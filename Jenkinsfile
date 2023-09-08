pipeline {

    agent any

 

    stages {

        stage('Build') {

            steps {

                echo "Building"

            }

        }

        stage('Unit and Integration Tests') {

            steps {

                echo "Unit Testing"

            }

             post {

                success {

                    mail to: "drpahwa25@gmail.com",

                    subject: "Test success",

                    body: "Test Success"

                }

            }

        }

        stage('Code Analysis') {

            steps {

                echo "Running Code Analysis"

            }

        }

    }

}