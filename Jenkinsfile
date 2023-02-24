pipeline {
    agent any

    stages {
        stage('clone github code') {
            steps {  
		       sh 'pwd'
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
       stage('deploy') {
            steps {
                sh 'sudo cp target/*.war /usr/share/tomcat/webapps/'
            }		
        }	    
    }
}
