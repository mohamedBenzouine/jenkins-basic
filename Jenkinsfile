pipeline {
    agent any

    stages {
        stage('Lint and Format') {
            steps {
                script {
                    stage('Linting') {
                        echo "Linting code in nested stage"
                    }
                    stage('Formatting') {
                        echo "Formatting code in nested stage"
                    }
                }
            }
        }

        stage('Setup') {
            steps {
                withCredentials([usernamePassword(credentialsId: 'server-cred', usernameVariable: "myuser", passwordVariable: "mypassword")]) {
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
