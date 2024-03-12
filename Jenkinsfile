pipeline {
    agent any
    stages {
        stage('Clone repository') {
            steps {
                git url: 'https://github.com/HamdaMustafa/MLOPSTASK3.git', branch: 'main'
            }
        }
        stage('Install dependencies') {
            steps {
                script {
                    // Use sh for Linux/Mac and bat for Windows
                    bat 'pip install -r requirements.txt'
                }
            }
        }
        stage('Execute test.py') {
            steps {
                script {
                    bat 'python test.py'
                }
            }
        }
        stage('Deploy') {
            steps {
                script {
                    if (env.BRANCH_NAME == 'main') {
                        echo 'Deploying to production'
                        
                    } else {
                        echo 'Deploying to UAT'
                        
                    }
                }
            }
        }
    }
}
