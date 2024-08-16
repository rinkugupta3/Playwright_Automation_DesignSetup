pipeline {
    agent any
    stages {
        stage('Checkout') {
            steps {
                git branch: 'main', url: 'https://github.com/rinkugupta3/Playwright_Automation_DesignSetup'
            }
        }
        stage('Set up Python environment') {
            steps {
                bat "C:/Users/dhira/AppData/Local/Programs/Python/Python311/python.exe -m pip install -r requirements.txt"
            }
        }
        stage('Install Playwright Browsers') {
            steps {
                bat "C:/Users/dhira/AppData/Local/Programs/Python/Python311/python.exe -m playwright install"
            }
        }
        stage('Dev - Run Playwright Tests') {
            steps {
                bat "C:/Users/dhira/AppData/Local/Programs/Python/Python311/python.exe -m pytest"
            }
        }
    }
    post {
        always {
            echo 'Cleaning up...'
            // Any clean-up steps you need to perform
        }
        success {
            echo 'Pipeline succeeded!'
        }
        failure {
            echo 'Pipeline failed!'
        }
    }
}

