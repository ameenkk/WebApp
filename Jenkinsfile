pipeline {
    agent any
    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/YOUR_GITHUB_USER/YOUR_REPO.git'
            }
        }
        stage('Build') {
            steps {
                script {
                    echo "Building the application..."
                    // Run build commands (if necessary)
                }
            }
        }
        stage('Deploy to IIS') {
            steps {
                script {
                    def iisPath = "C:\\inetpub\\wwwroot\\mywebapp"
                    bat "rmdir /S /Q ${iisPath}"
                    bat "mkdir ${iisPath}"
                    bat "xcopy /E /I /Y . ${iisPath}"
                }
            }
        }
        stage('Restart IIS') {
            steps {
                script {
                    bat "iisreset"
                }
            }
        }
    }
}
