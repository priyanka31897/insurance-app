pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-jenkins',
                    url: 'https://github.com/priyanka31897/insurance-app.git'
            }
        }
        stage('Deploy') {
            steps {
                sh '''
                sudo mkdir -p /var/www/html
                sudo cp index.html /var/www/html/index.html
                '''
            }
        }
    }
}
