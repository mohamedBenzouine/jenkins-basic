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
        sh 'sudo apt update && sudo apt install -y python3 python3-pip'
        sh 'sudo pip install -r requirement.txt'
        }
        }

        stage('Test') {
            steps {
                sh "pytest"
                
            }
        }    
      
    }
}