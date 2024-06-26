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
                sh 'echo "Service user is $username_pass_workstation_USR"'
                sh 'echo "Service password is $username_pass_workstation_PSW"'
                
            }
        }
    
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
