pipeline {
    agent {
        label 'agent-1'
    }

    // options{
    //     timeout(time:10, unit: 'Seconds')
    //     disableCouncurrentBuild()
    //     retry(1)
    // }

    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')
        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')
        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')
        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')
        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
        stage('Print params') {
            steps {
                echo "Hello ${params.PERSON}"
                echo "Biography: ${params.BIOGRAPHY}"
                echo "Toggle: ${params.TOGGLE}"
                echo "Choice: ${params.CHOICE}"
                echo "Password: ${params.PASSWORD}"
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