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
                echo ' I will always say Hello again '
            }
            failure {
                echo ' I will always run when the above pipeline is FAILURE '
            }
            success {
                echo ' I will run always when the above pipeline is SUCCESS '
            }
            abort {
                echo 'I will run when the pipeline is ABORT'
            }

        }
        

    }
}