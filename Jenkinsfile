pipeline {
    agent any

    stages {
        stage('clone github code') {
            steps {
		sh 'rm -rf *'    
                sh 'git clone https://github.com/rajulucky812/jenkins-docker-project.git' 
		sh    'pwd'
                  }
	}

        stage('compile') {
          steps {
           sh 'mvn compile'         
           }
			}
       stage('package') {
            steps {
                 sh 'pwd'
                sh 'mvn package'
            }		
        }
    }
}
