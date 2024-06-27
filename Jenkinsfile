pipeline {
    agent { node { label 'workspace' } } 
    environment { 
        CC = 'clang'
    }
    options { checkoutToSubdirectory('hello') }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: '', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('Build') {
            steps {
                sh 'echo Build'
                sh 'echo second line'
                sh 'echo "$CC"'
                sh 'env'
                sh 'pwd'
            }
        }
    stage('test') {
        environment{
            CRED = credentials("username_pass_workstation")
        }
            steps {
                sh 'echo "Service user is $CRED_USR"'
                sh 'echo "Service password is $CRED_PSW"'
                
            }
        }
    
    }

    post { 
        always { 
            echo 'I will always say Hello again!'
        }
    }
}
