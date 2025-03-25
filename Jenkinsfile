pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git url: 'https://github.com/ameenkk/WebApp.git',
                    credentialsId: 'your-jenkins-credential-id'
            }
        }
    }
}
