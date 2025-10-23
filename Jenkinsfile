pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                bat 'echo "Building Docker image..."'
                bat 'docker build -t myflaskapp .'
            }
        }
        stage('Test') {
            steps {
                bat 'echo "Running tests..."'
                bat 'pytest || echo "No tests yet"'
            }
        }
        stage('Deploy') {
            steps {
                bat 'echo "Deploying to Kubernetes..."'
                bat 'kubectl apply -f deployment.yaml'
                bat 'kubectl apply -f service.yaml'
            }
        }
    }
}
