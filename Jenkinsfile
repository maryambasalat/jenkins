flag = true
pipeline {
    agent any
        tools{
            maven "Maven"
        }
    environment {
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
                echo "Building version ${NEW_VERSION}"
                sh "nvm install"
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            when {
                expression {
                    flag == false
                }
            }
            steps {
                echo 'Deploying....'
            }
        }
    }
    post {
        always {
            echo 'This block always runs.'
        }
        failure {
            echo 'This block runs only on failure.'
        }
    }
}
