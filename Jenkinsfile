pipeline {
    agent any

    stages {

        stage('lint and format')
            parallel {
                stage('linting'){
                    steps{
                        echo "linting code in nested stage"
                    }
                }

                stage('formating'){
                    steps {
                        echo "formating code in nested stage"
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