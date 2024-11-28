pipeline {
    agent any
    parameters {
        // These are types of parameters
        string(name: 'VERSION', defaultValue: '', description: 'Version to deploy on prod')
        choice(name: 'VERSION', choices: ['1.1.0', '1.2.0', '1.3.0'], description: '')
        booleanParam(name: 'executeTests', defaultValue: true, description: '')
    }
    environment {
        // Variables defined here can be used by any stage
        NEW_VERSION = '1.3.0'
    }
    stages {
        stage('build') {
            steps {
                echo 'Building Project'
            }
        }
        stage('test') {
            when {
                expression {
                    params.executeTests
                }
            }
            steps {
                echo 'Testing Project'
            }
        }
    }
}
