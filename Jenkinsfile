pipeline {
    agent any
    environment {
        EXAMPLE_CREDS = credentials('example-credentials-id')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                echo "Asukwo in charge..."
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
                echo "Building"
            }
        }
		stage('credentials') {
            steps {
                /* CORRECT */
                sh'''
                echo "i can build"
                ls -al

                pwd

                printenv | grep EXAMPLE_CREDS
                '''
            }
        }
    }
}
