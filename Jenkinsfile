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
                echo "Static website - no build required."
            }
        }

        stage('Deploy') {
            steps {
                echo "Deploying website to Deploy folder..."
                bat 'if not exist "C:\\Users\\Student\\Desktop\\Portfolio\\Deploy" mkdir "C:\\Users\\Student\\Desktop\\Portfolio\\Deploy" && xcopy /E /I /Y * "C:\\Users\\Student\\Desktop\\Portfolio\\Deploy\\"'
            }
        }
    }

    post {
        success {
            echo "✔ Deployment Successful!"
        }
        failure {
            echo "✖ Deployment Failed!"
        }
    }
}
