pipeline {
    agent any

    environment {
        DEPLOY_DIR = 'C:\\xampp\\htdocs\\my-static-site'  // XAMPP default path on Windows
    }

    stages {
        stage('Clone Repository') {
            steps {
                git branch: 'main', url: 'https://github.com/Srvshkdm/my-static-site.git'
            }
        }

        stage('Build') {
            steps {
                echo 'No build step needed for static HTML files.'
            }
        }

        stage('Deploy') {
            steps {
                bat """
                if not exist "%DEPLOY_DIR%" mkdir "%DEPLOY_DIR%"
                copy /Y *.html "%DEPLOY_DIR%"
                """
            }
        }
    }

    post {
        success {
            echo 'Deployment to XAMPP on Windows successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
