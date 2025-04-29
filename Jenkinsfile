pipeline {
    agent any

    environment {
        DEPLOY_DIR = '/opt/lampp/htdocs/my-static-site'
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
                sh """
                    mkdir -p ${DEPLOY_DIR}
                    cp -v *.html ${DEPLOY_DIR}
                """
            }
        }
    }

    post {
        success {
            echo 'Deployment to XAMPP successful!'
        }
        failure {
            echo 'Deployment failed.'
        }
    }
}
