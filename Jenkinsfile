pipeline {
    agent any

    environment{
        SERVER_CREDS = credentials('server-cred')
    }

    stages {

        stage('Setup'){
            steps{
                echo "my creds: ${SERVER_CREDS}"
                echo "Username: ${SERVER_CREDS_USR}"
                echo "password: ${SERVER_CREDS_PSW}"
                sh "pip install -r requirements.txt"
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