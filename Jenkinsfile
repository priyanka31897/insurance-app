pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    credentialsId: 'github-token',
                    url: 'https://github.com/priyanka31897/insurance-app.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                sudo dnf install -y nginx
                sudo systemctl start nginx
                sudo systemctl enable nginx
                sudo mkdir -p /usr/share/nginx/html
                sudo cp ~/insurance-app/index.html /usr/share/nginx/html/index.html
                '''
            }
        }
    }
}
