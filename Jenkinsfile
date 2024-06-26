pipeline {
    agent { node { label 'workspace' } } 
    environment { 
        CC = 'clang'
    }

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                echo 'second line'
                echo CC
            }
        }
    stage('test') {
        environment{
            CRED = credentials("username_pass_workstation")
        }
            steps {
                echo CRED
                echo 'intentional error'
                echo '${CRED}'
                echo '${env}'
                sh 'printenv'
            }
        }
    
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
