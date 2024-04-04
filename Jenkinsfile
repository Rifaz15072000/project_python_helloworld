pipeline {
    agent any

    stages {
        stage('Build Docker Image') {
            steps {
                script {
                    // Build the Docker image
                    docker.build('my_flask_app')
                }
            }
        }

        stage('Run Tests') {
            steps {
                // Run tests (if applicable)
                sh 'echo "Running tests..."'
            }
        }

        stage('Deploy Application') {
            steps {
                // Stop and remove existing container
                sh 'docker stop my_flask_app_container || true'
                sh 'docker rm my_flask_app_container || true'

                // Run the Docker container
                sh 'docker run -d -p 5000:5000 --name my_flask_app_container my_flask_app'
            }
        }
    }
}
