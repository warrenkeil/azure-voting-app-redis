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
        stage('Docker Build'){
            steps{
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