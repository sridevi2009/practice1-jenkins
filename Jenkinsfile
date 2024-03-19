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
        disableConcurrentBuilds()
        ansiColor ('xterm') 
    }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
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
                    echo "$GREETING"
                   
                   # sleep 10   
                """
            }
        }
        stage('params') {
            steps {
                sh """

                    echo "Hello ${params.PERSON}"

                    echo "Biography: ${params.BIOGRAPHY}"

                    echo "Toggle: ${params.TOGGLE}"

                    echo "Choice: ${params.CHOICE}"

                    echo "Password: ${params.PASSWORD}"
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