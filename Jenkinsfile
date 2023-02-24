pipeline {
    agent any

    stages {
        stage('clone github code') {
            steps {  
              //  sh 'git clone https://github.com/rajulucky812/jenkins-docker-project.git ./jenkins-docker-project' 
		       sh 'pwd'
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
       stage('deploy') {
            steps {
                sh 'sudo cp target/*.war /usr/share/tomcat/webapps/'
            }		
        }	    
    }
}
