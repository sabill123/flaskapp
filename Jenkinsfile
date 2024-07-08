pipeline {

    agent any

    environment {

        DOCKER_USER_ID = credentials('docker_user_id')  // Jenkins Credential ID

        DOCKER_PASSWORD = credentials('docker_token')   // Jenkins Credential ID

    }



    stages {

        stage('Build') {

            steps {

                echo 'Building the application...'

                sh 'make build'

            }

        }

        stage('Test') {

            steps {

                echo 'Testing the application...'

                sh 'make test'

            }

        }

        stage('Deploy') {

            steps {

                echo 'Deploying the application...'

                sh 'make deploy'

            }

        }

    }



    post {

        always {

            echo 'This will always run'

        }

        success {

            echo 'This will run only if successful'

        }

        failure {

            echo 'This will run only if failed'

        }

    }

}


