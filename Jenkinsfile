pipeline {
    agent {label 'docker-agent-python'}
    environment {
        EXAMPLE_CREDS = credentials('example-credentials-id')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploy....'
            }
        }
		stage('credentials') {
            steps {
                /* CORRECT */
                sh'''
                ls -al

                printenv | grep EXAMPLE_CREDS
                '''
            }
        }
    }
}