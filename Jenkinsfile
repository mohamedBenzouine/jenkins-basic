pipeline {
    agent any

    stages {

        stage('lint and format'){
            parallel {
                stage('linting'){
                    steps{
                        sh "sleep 30"
                    }
                }

                stage('formating'){
                    steps{
                        sh "sleep 30"
                    }
                }
            }
        }

        stage('Setup'){
            steps {
                withCredentials([usernamePassword(credentialsId: 'server-cred', usernameVariable: "myuser", passwordVariable: "mypassword")]){
                    sh '''
                    echo ${myuser}
                    echo ${mypassword}
                    '''
                }
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