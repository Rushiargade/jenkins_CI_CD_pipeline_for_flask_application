pipeline {
    agent any

    stages {

        stage('Build') {
            steps {
                sh '''
                python3 -m venv venv
                . venv/bin/activate
                pip install --upgrade pip
                pip install -r requirements.txt
                '''
            }
        }

        stage('Test') {
            steps {
                sh '''
                . venv/bin/activate
                pytest -v
                '''
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                echo "Deploying Flask application..."
                nohup python3 app.py &
                '''
            }
        }
    }

    post {
        success {
            echo "Build Successful"
        }
        failure {
            echo "Build Failed"
        }
    }
}
