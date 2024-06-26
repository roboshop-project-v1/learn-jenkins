pipeline {
    agent { node { label 'workspace' } } 

    stages {
        stage('Build') {
            steps {
                echo 'Build'
                echo 'second line'
            }
        }
    stage('test') {
            steps {
                error 'intentional error'
            }
        }
    
    
    }
}
