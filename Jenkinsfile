pipeline {
    agent any

    stages {

        stage('Setup Server') {
            steps {
                sh '''
                sudo apt update
                sudo apt install nginx -y
                '''
            }
        }

        stage('Clone Website') {
            steps {
                sh 'git clone https://github.com/HrishiNMore/jenkins.git'
            }
        }

        stage('Deploy Website') {
            steps {
                sh '''
                sudo cp -r jenkins/* /var/www/html/
                sudo systemctl restart nginx
                '''
            }
        }

    }
}