
pipeline {
    agent any

    environment {
        PATH = "/usr/bin:/bin:/opt/homebrew/bin"
    }

    stages {

        stage('compile stages') {
            steps {
                sh 'mvn compile'
            }
        }

        stage('build') {
            steps {
                sh 'mvn clean install'
            }
        }

        stage('Deploy') {
            when {
                expression {
                    env.BRANCH_NAME?.contains('release')
                }
            }
            stage('PR Change Demo') {
    steps {
        echo 'Testing a new change through Pull Request'
    }
}
            steps {
                echo "Its an release branch and will start deploy the war to tomcat"
            }
        }
    }

    post {
        success {
            echo 'Build success 1'
        }

        failure {
            echo 'Failure in the build'
        }
    }
}
