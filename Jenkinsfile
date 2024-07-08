pipeline {

    agent any

    environment {

        NEW_VERSION = '1.0.0'

    }

    stages {

        stage('Build') {

            steps {

                echo 'Building the application...'

                echo "Building version ${NEW_VERSION}"

                sh 'make build'

            }

        }

        stage('Test') {

            when {

                branch 'main'

            }

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


