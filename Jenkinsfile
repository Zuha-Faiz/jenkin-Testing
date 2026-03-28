pipeline {
    agent any

    stages {

        stage('Install Dependencies') {
            steps {
                bat 'pip install -r requirements.txt || echo No dependencies'
            }
        }

        stage('Run Tests') {
            steps {
                bat 'python -m unittest discover -s tests -p "test_*.py" -v'
            }
        }

    }

    post {
        success {
            echo 'Tests Passed'
        }
        failure {
            echo 'Tests Failed'
        }
    }
}