pipeline {
    agent {
        node {
            label 'AGENT-1'
        }
    }
    environment {
        Greetings = "Hi I am environmental variable"
    }
    options {
        // Timeout counter starts AFTER agent is allocated
        timeout(time: 100, unit: 'SECONDS')
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
                echo 'Deploying the code....'
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
