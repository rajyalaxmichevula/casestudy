pipeline {
    agent any
    stages {
        stage('Build') {
            steps {
                sh 'echo "Building Docker image..."'
                sh 'docker build -t myflaskapp .'
            }
        }
        stage('Test') {
            steps {
                sh 'echo "Running tests..."'
                sh 'pytest || echo "No tests yet"'
            }
        }
        stage('Deploy') {
            steps {
                sh 'echo "Deploying to Kubernetes..."'
                sh 'kubectl apply -f deployment.yaml'
                sh 'kubectl apply -f service.yaml'
            }
        }
    }
}
