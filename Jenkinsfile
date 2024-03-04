pipeline {
    agent { node { label 'Agent' } }
    stages {
        stage{'Install depdencies'} {
            steps {
                sh 'npm install'
            }
        }
        stage('unit test') {
            steps {
                echo "unit testing is done here"
            }
        }
        
    }
}

    
