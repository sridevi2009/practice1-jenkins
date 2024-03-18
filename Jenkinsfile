pipeline {
    agent  {
        node {
            label 'agent'
        }
    }
    

    stages {
        stage('clone') {
            steps {
                echo 'clone the code'
            }
        }
        stage('build') {
            steps {
                echo 'install dependecies'
            }
        }
         stage('testing') {
            steps {
                echo 'testing the code'
            }
        }
         stage('deploy') {
            steps {
                echo 'deploying the code'
            }
        }
        post { 
            always { 
                echo 'I will always say Hello again!'
            }
            success {
                echo 'I will run when pipeline is SUCCESS'

            }
            failure {
                echo ' I will run when above pipeline is FAILURE'
            }
            abort {
                echo 'I will run when the above pipeline is ABORTED'
            }
        }    

       
    }
}