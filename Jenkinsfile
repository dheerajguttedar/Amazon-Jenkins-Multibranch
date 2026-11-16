pipeline {
    agent any

    stages {
        stage('Build') {
            steps {
                echo 'Building application'
            }
        }

        stage('Testing') {
            steps {
                echo 'Testing automatic branch build'
            }
        }
    }

    post {
        success {
            echo 'Build success'
        }
        failure {
            echo 'Failure in the build'
        }
    }
}
