pipeline {
    agent any
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
                echo "Deploy...."
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
    post {
        success {
            emailext (
                to: 'aboludepeter@gmail.com',
                subject: 'Build Successful: ${currentBuild.fullDisplayName}',
                body: 'The build ${currentBuild.fullDisplayName} succeeded.',
                recipientProviders: [developers()]
            )
        }
    }
}
