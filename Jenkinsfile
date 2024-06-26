pipeline {
    agent { node { label 'workspace' } } 

    stages {
        stage('Build') {
            steps {
                echo 'Build'
            }
        }
    stage('test') {
            steps {
                error 'intentional error'
            }
        }
    
    
    }
}
