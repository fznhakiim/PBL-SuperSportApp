pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/fznhakiim/PBL-SuperSportApp.git'
            }
        }
        stage('Build') {
            steps {
                echo 'Building the project...'
            }
        }
        stage('Test') {
            steps {
                echo 'Running tests...'
            }
        }
        stage('Push Changes') {
            steps {
                script {
                    sh '''
                    #!/bin/bash
                    REPO_PATH=$(pwd)  # Path ke workspace Jenkins
                    cd $REPO_PATH

                    # Tambahkan perubahan dan commit
                    git add .
                    git commit -m "Auto commit by Jenkins at $(date)"

                    # Push ke branch main
                    git push origin main
                    '''
                }
            }
        }
    }
    post {
        always {
            echo 'Pipeline execution completed!'
        }
    }
}
