pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    // Build
    stages {
        stage('Build') {
            steps {
                echo 'Building..'
            }
        }
        stage('Test') {
            steps {
                echo 'Testing..'
            }
        }
        stage('Deploy') {
            steps {
                echo 'Deploying....'
            }
        }
    }
    // Post Build
    post {
        always {
            echo 'I will always execute this after build success'
        }
    }
}
