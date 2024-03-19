pipeline {
    agent  {
        node {
            label 'agent'
        }
    }
    environment { 
        GREETING = 'Hello -JENKINS'
    }
    options {
        timeout(time: 1, unit: 'HOURS')
        ansiColor ('xterm') 
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
                sh """
                    echo " I will run shell-script here "
                    env   
                """
            }
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
        aborted {
            echo 'I will run when the pipeline is ABORT'
        }

    }
}