pipeline {
    agent any
    environment {
        NEW_VERSION = '1.3.0'
        // EXAMPLE_CREDS = credentials('example-credentials-id')
    }
    stages {
        stage('Build') {
            steps {
                echo "Building.."
                echo "version is ${NEW_VERSION}"
            }
        }
        stage('Test') {
            steps {
                echo "Testing.."
            }
        }
        stage('Deploy') {
            steps {
                echo "Deploy.."
                withCredentials([
                    usernamePassword(credentials: 'example-credentials-id', usernameVariable: USER, passwordVariable: PWD)
                ]){
                    sh "some script ${USER} ${PWD}"
                }
            }
        }
    }
}
