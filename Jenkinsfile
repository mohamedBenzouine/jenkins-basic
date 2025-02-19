pipeline {
    agent any
    stages {
        stage('Checkout'){
            steps{
                git url: 'https://github.com/mohamedBenzouine/jenkins-basic.git', branch:'main'
                sh "ls -ltr"
            }
        }


        stage('Setup') {
            steps {
                sh "pip install -r requirement.txt"
            }
        }
        stage('Test') {
            steps {
                sh "pytest"
                
            }
        }    
      
    }
}