pipeline {
    agent { label 'agentlinux' }
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/priyanka31897/insurance-devops-project.git'
            }
        }
        stage('Setup Python') {
            steps {
                sh '''
                python3 -m venv venv
                source venv/bin/activate
                pip install --upgrade pip
                pip install flask
                '''
            }
        }
        stage('Run App') {
            steps {
                sh '''
                source venv/bin/activate
                python3 app.py
                '''
            }
        }
    }
}
