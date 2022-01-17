pipeline {
    agent any

    stages {
        stage('Verify Branch') {
            steps {
                echo "$GIT_BRANCH"
            }
        }
        stage('Test shell script'){
            steps{
                sh(script:'echo "Hi from shell script"')
            }
        }
        stage('Test docker command'){
            steps{
                sh '''docker ps'''
            }
        }
        stage('Docker Build'){
            steps{
                sh'docker images -a'
                sh(script: """
                cd azure-vote/
                docker images -a
                docker build -t jenkins-pipeline .
                docker images -a
                cd .. 
                """)
            }
        }
    }
}