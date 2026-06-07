pipeline {
    agent any
    stages {

        stage('Clone Code') {
            steps {
                git branch: 'main',
                    url: 'https://github.com/akhilapoosarla622-hub/CICD-Automation.git'
            }
        }

        stage('Build') {
            steps {
                echo 'Building HTML project...'
            }
        }

        stage('Test') {
            steps {
                echo 'Testing website files...'

                sh '''
                if [ -f index.html ]; then
                    echo "index.html exists"
                else
                    echo "index.html missing"
                    exit 1
                fi
                '''
            }
        }

        stage('Deploy') {
            steps {
                echo 'Deploying website...'

                sh '''
                sudo cp -r * /var/www/html/
                '''
            }
        }
    }
}
