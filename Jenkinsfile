pipeline {
    agent any
    stages {
        stage('Build') {
            steps{
                sh 'echo this is build'
            }
        }
        stage('Test') {
            steps{
                sh 'echo this is test'
            }
        }
        stage('Deploy') {
            steps{
                 sh 'echo this is Deploy'
            }
        }
    }
    post {
        always{
            echo " Build update: this section runs always"
        }
        success{
            echo " Build Sucess: this section run when pipeline sucesss"
        }
        failure{
            echo "build failed: this section run when pipeline failed"
        }
    }
}