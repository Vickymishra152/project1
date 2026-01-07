pipeline {
    agent any

    stages {
        stage('Install Dependencies') {
            steps {
               sh '''
	       python3 -m venv venv
               . venv/bin/activate
               pip install --upgrade pip
               pip install -r requirements.txt
               '''
 


            }
        }

        stage('Run Tests') {
            steps {
                sh '''
                . venv/bin/activate
                python -m unittest test_app.py
                '''
            }
        }
    }

    post {
        always {
            echo 'Build Finished'
        }
    }
}

