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
        string(name: 'SRIDEVI', defaultValue: 'HELLO-jenkins', description: 'Who should I say hello to?')

        text(name: 'GOPI', defaultValue: 'hi\nim gopi\nworking in pharmacy in banglore\ndo u required some offers\n', description: 'Enter some information about the person')

        booleanParam(name: 'Deploy-Dev', defaultValue: true, description: 'Deploy-Dev this value')

        choice(name: 'ENV_DEV', choices: ['apply', 'destroy'], description: 'Pick something')

        password(name: 'DEVOPS', defaultValue: 'DEVOPS321', description: 'Enter a password')
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
                
                echo "Sridevi ${params.SRIDEVI}"

                echo "Gopi: ${params.GOPI}"

                echo "Deploy-dev: ${params.Deploy-Dev}"

                echo "Env-dev: ${params.ENV-DEV}"

                echo "Devops: ${params.DEVOPS}"
                    
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