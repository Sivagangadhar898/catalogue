pipeline {
    agent { node { label 'Agent' } }
    stages {
        stage{'Install dependencies'} {
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

    
