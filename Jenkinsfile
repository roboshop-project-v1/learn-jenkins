pipeline {
    agent { node { label 'workspace' } } 

    stages {
        stage('Build') {
            steps {
                echo 'Build'
            }
            steps {
                echo 'Build step2'
            }
            steps {
                echo 'Build step3'
            }
        }
    stage('test') {
            steps {
                error 'intentional error'
            }
        }
    
    
    }
}
