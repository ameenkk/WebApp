pipeline {
    agent any

    environment {
        GIT_REPO = 'https://github.com/ameenkk/WebApp.git'
        CREDENTIALS_ID = 'fdf1688a-d51d-4d34-aef3-5365139046a2'  // Replace with your Jenkins credentials ID
    }

    stages {
        stage('Checkout') {
            steps {
                git url: GIT_REPO, credentialsId: CREDENTIALS_ID, branch: 'main'
            }
        }

        stage('Build') {
            steps {
                script {
                    // Example for a Maven build
                    sh 'mvn clean package'
                    
                    // If using Gradle
                    // sh './gradlew build'
                }
            }
        }

        stage('Test') {
            steps {
                script {
                    // Example for running unit tests with Maven
                    sh 'mvn test'

                    // If using Gradle
                    // sh './gradlew test'
                }
            }
        }

        stage('Deploy') {
            steps {
                script {
                    // Simulated deployment step (Modify as needed)
                    sh 'echo "Deploying application..."'
                    
                    // Example: Copy to a server (modify accordingly)
                    // sh 'scp target/myapp.jar user@server:/path/to/deploy/'
                }
            }
        }
    }

    post {
        success {
            echo 'Pipeline executed successfully!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}
