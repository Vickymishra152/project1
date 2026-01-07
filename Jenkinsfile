pipeline {
    agent {
        docker { image 'python:3.11-slim' }
    }

    stages {
        stage('Install Dependencies') {
            steps {
                sh 'pip install --upgrade pip'
                sh 'pip install -r requirements.txt'
            }
        }

        stage('Run Tests') {
            steps {
                sh 'python -m unittest test_app.py'
            }
        }
    }

    post {
        always {
            echo 'Build Finished'
        }
    }
}

