pipeline {
    agent any

    environment {
        APP_NAME = "NexTask"
        DEPLOY_DIR = "/var/www/html"
        BUILD_VERSION = "${BUILD_NUMBER}"
    }

    stages {

        stage('Clone Repository') {
            steps {
                echo "=========================================="
                echo " Cloning ${APP_NAME} from GitHub..."
                echo "=========================================="
                git branch: 'main', url: 'https://github.com/YOUR_USERNAME/devops-web-project.git'
            }
        }

        stage('Verify Files') {
            steps {
                echo "=========================================="
                echo " Verifying project structure..."
                echo "=========================================="
                sh '''
                    echo "Project files:"
                    ls -la
                    echo ""
                    echo "Source files:"
                    ls -la src/
                '''
            }
        }

        stage('Test') {
            steps {
                echo "=========================================="
                echo " Running tests..."
                echo "=========================================="
                sh '''
                    # Check index.html exists
                    if [ -f src/index.html ]; then
                        echo "✅ index.html found"
                    else
                        echo "❌ index.html missing!"
                        exit 1
                    fi

                    # Check file is not empty
                    if [ -s src/index.html ]; then
                        echo "✅ index.html is not empty"
                    else
                        echo "❌ index.html is empty!"
                        exit 1
                    fi

                    echo ""
                    echo "All tests passed ✅"
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo "=========================================="
                echo " Deploying to web server..."
                echo "=========================================="
                sh '''
                    sudo cp -r src/* /var/www/html/
                    echo "✅ Deployed successfully to ${DEPLOY_DIR}"
                '''
            }
        }

        stage('Verify Deployment') {
            steps {
                echo "=========================================="
                echo " Verifying deployment..."
                echo "=========================================="
                sh '''
                    if [ -f /var/www/html/index.html ]; then
                        echo "✅ Deployment verified - index.html live!"
                    else
                        echo "❌ Deployment verification failed!"
                        exit 1
                    fi
                '''
            }
        }
    }

    post {
        success {
            echo "=========================================="
            echo " ✅ Pipeline #${BUILD_NUMBER} SUCCESS!"
            echo " ${APP_NAME} deployed successfully."
            echo "=========================================="
        }
        failure {
            echo "=========================================="
            echo " ❌ Pipeline #${BUILD_NUMBER} FAILED!"
            echo " Check the logs above for errors."
            echo "=========================================="
        }
        always {
            echo "Pipeline finished at: ${new Date()}"
        }
    }
}
