pipeline {
        agent any
        triggers {
            githubPush()
        }
        stages {
            stage('Build') {
                steps {
                    echo 'Building...'
                    sh 'python3 -m venv venv'
                    sh '. venv/bin/activate && pip install -r requirements.txt'
                }
            }
            stage('Test') {
                steps {
                    echo 'Testing...'
                    sh '. venv/bin/activate && pytest tests/'
                }
            }
        }
    }
