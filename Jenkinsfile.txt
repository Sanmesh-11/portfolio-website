pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/Sanmesh-11/portfolio-website.git'
            }
        }

        stage('Build') {
            steps {
                echo "Static website - no build step required."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying website to IIS folder..."

                // Copy all website files to deployment directory
                bat """
                xcopy /E /Y * "C:\\inetpub\\wwwroot\\portfolio-website"
                """
            }
        }
    }

    post {
        success {
            echo "Deployment Successful!"
        }
    }
}
