pipeline {
    agent { node { label 'Agent-1' } }
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
                sh 'zip -r catalogue.zip ./*  --exclude=.git  --exclude=.zip'
            }
        }
        stage('publish Artifact') {
            steps {
                nexusArtifactUploader(
                    nexusVersion: 'nexus3',
                    protocol: 'http',
                    nexusUrl: '3.234.227.62:8081/',
                    groupId: 'com.roboshop',
                    version: '1.0.0',
                    repository: 'catalogue',
                    credentialsId: 'nexus-ssh',
                    artifacts: [ 
                        [artifactId: 'catalogue',
                        classifier: '',
                        file: 'catalogue.zip',
                        type: 'zip']
                        
                    ]
                )
           }
        }
    }  
       
    post{
        always{
            echo 'cleaning up workspace'
            deleteDir()
        }
                

    }
}




    
