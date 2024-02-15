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
    parameters {
        booleanParam(name: "TEST_BOOLEAN", defaultValue: true, description: "Sample boolean parameter")
        string(name: "TEST_STRING", defaultValue: "ssbostan", trim: true, description: "Sample string parameter")
        text(name: "TEST_TEXT", defaultValue: "Jenkins Pipeline Tutorial", description: "Sample multi-line text parameter")
        password(name: "TEST_PASSWORD", defaultValue: "SECRET", description: "Sample password parameter")
        choice(name: "TEST_CHOICE", choices: ["production", "staging", "development"], description: "Sample multi-choice parameter")
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
