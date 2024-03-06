pipeline {
    agent { node { label 'Agent' } }
    stages {
        stage('Install depdencies') {
            steps {
                sh 'npm install'
            }
        }
        stage('unit test') {
            steps {
                echo "unit testing is done here"
            }
        } 
        // stage('sonar scan') {
        //     steps {
        //         sh 'ls -ltr'
        //         sh 'sonar-scanner'
        //     }
        // }
        stage ('build') {
            steps {
                sh 'ls -ltr'
                sh 'zip -r ./*  --exclude=.git  --exclude=.zip'
            }
        }
        
    }
}

    
