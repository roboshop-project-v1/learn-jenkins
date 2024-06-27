pipeline {
    agent { node { label 'workspace' } } 
    environment { 
        CC = 'clang'
    }
    options { checkoutToSubdirectory('hello') }
    parameters {
        string(name: 'PERSON', defaultValue: 'Mr Jenkins', description: 'Who should I say hello to?')

        text(name: 'BIOGRAPHY', defaultValue: 'k', description: 'Enter some information about the person')

        booleanParam(name: 'TOGGLE', defaultValue: true, description: 'Toggle this value')

        choice(name: 'CHOICE', choices: ['One', 'Two', 'Three'], description: 'Pick something')

        password(name: 'PASSWORD', defaultValue: 'SECRET', description: 'Enter a password')
    }

    stages {
        stage('Example') {
            steps {
                echo "Hello ${params.PERSON}"

                echo "Biography: ${params.BIOGRAPHY}"

                echo "Toggle: ${params.TOGGLE}"

                echo "Choice: ${params.CHOICE}"

                echo "Password: ${params.PASSWORD}"
            }
        }

        stage('Build') {
            input {
            message "Should we continue?"
            ok "Yes, we should."
            submitter "alice,bob"
            }

            steps {
                sh 'echo Build'
                sh 'echo second line'
                sh 'echo "$CC"'
                sh 'env'
                sh 'pwd'
            }
        }
        stage('test') {
            when{
                branch 'main' 
            }
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
