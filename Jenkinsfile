pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        Greetings = "Hi I am environmental variable"
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
                sh """
                echo 'Deploying....'
                echo '$Greetings'
                """
            }
        }
    }
    // Post Build
    post {
        always {
            echo 'I will always execute this after build success'
        }
        failure {
            echo 'Build successfully failed'
        }
        success {
            echo 'Build completed successfully'
        }
    }
}
