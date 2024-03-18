pipeline {
    agent  {
        node {
            label 'agent'
        }
    }
    

    stages {
        stage('clone') {
            steps {
                echo 'Hello Hyderabad'
            }
        }
        stage('build') {
            steps {
                echo 'Hello Hyderabad, Good morning'
            }
        }
         stage('test') {
            steps {
                echo 'Hello banglore, Good eve'
            }
        }
         stage('deploy') {
            steps {
                echo 'Hello Hyderabad, Good night'
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