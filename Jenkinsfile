pipeline {
    agent any

    stages {
        stage('clone github code') {
            steps {  
                sh 'git clone https://github.com/rajulucky812/jenkins-docker-project.git ./jenkins-docker-project' 
                  }
	}

        stage('compile') {
          steps {
           sh 'cd ./jenkins-docker-project'
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
