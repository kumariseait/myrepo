pipeline {
    agent any

    stages {
        stage('Clone Repository') {
            steps {
                // Clone the repository containing your webpage
                git 'https://github.com/kumariseait/myrepo.git'
            }
        }

        stage('Deploy Webpage') {
            steps {
                script {
                    // Simple example to copy the HTML to a folder
                    sh '''
                    mkdir -p /var/www/html/simple-webpage
                    cp index.html /var/www/html/simple-webpage/
                    '''
                }
            }
        }

        stage('Verify Deployment') {
            steps {
                script {
                    // Check if the file exists (basic verification)
                    sh 'ls /var/www/html/simple-webpage'
                }
            }
        }
    }

    post {
        success {
            echo 'Webpage successfully deployed!'
        }

        failure {
            echo 'Deployment failed.'
        }
    }
}
