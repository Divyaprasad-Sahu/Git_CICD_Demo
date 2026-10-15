pipeline {
    agent any
    options { timestamps() }
    stages {
        stage('Checkout') {
            steps { checkout scm }
        }
        stage('Setup and Test') {
            steps {
                sh 'python3 -m venv .venv'
                sh '.venv/bin/python -m pip install -r requirements-dev.txt'
                sh '.venv/bin/python -m pytest -v'
            }
        }
    }
}
