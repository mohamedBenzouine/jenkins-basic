pipeline {
    agent any

    stages {

        stage('Checkout'){
            steps{
                git url:'https://github.com/mohamedBenzouine/jenkins-basic.git',branch:'main'
                sh "ls -ltr"
            }
        }

        stage('Setup'){

            environment {
                DB_HOST = '192.168.12.1'
                USERNAME = 'user1'
                PASSWORD = 'password123'
    }
            steps{
                sh "pip install -r requirements.txt"
                echo "the database IP is: ${DB_HOST}"
            }
        }

        stage('Test') {
            steps {
                sh "pytest"
                echo "Commit: ${env.GIT_COMMIT}"
                
            }
        }    
      
    }
}