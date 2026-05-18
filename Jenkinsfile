pipeline {
    agent any

    stages {

        stage('Clone Repository') {
            steps {
                echo 'Cloning code from GitHub...'
                git branch: 'main', url: 'https://github.com/Kittycat8126/devops-web-project.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building the project...'
                sh 'ls -la src/'
            }
        }

        stage('Test') {
            steps {
                echo 'Running basic tests...'
                sh 'test -f src/index.html && echo "index.html exists - Test Passed"'
            }
        }

        stage('Deploy to EC2') {
            steps {
                echo 'Deploying website to server...'
                sh 'sudo cp -r src/* /var/www/html/'
                echo 'Deployment complete!'
            }
        }
    }

    post {
        success {
            echo '✅ Pipeline executed successfully!'
        }
        failure {
            echo '❌ Pipeline failed. Check logs.'
        }
    }
}