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
        

    }
}