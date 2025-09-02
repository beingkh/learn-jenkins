pipeline {
    agent {
        label 'agent 1'
    }
    options{
        timeout(time:10, unit: 'Seconds')
    }
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
            deleteDir()
        }
        success{
            echo " Build Sucess: this section run when pipeline sucesss"
        }
        failure{
            echo " Build failed: this section run when pipeline failed"
        }
    }
}