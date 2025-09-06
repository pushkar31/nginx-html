pipeline {
    agent any

    stages {
        stage('Checkout') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/pushkar31/nginx-html.git'
            }
        }

        stage('Deploy') {
            steps {
                sh '''
                    echo "Copying index.html to Apache web directory..."
                    sudo cp index.html /var/www/html/index.html
                    echo "Restarting Apache..."
                    sudo systemctl restart apache2
                '''
            }
        }
    }
}