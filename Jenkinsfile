pipeline {
    agent any
    stages {
        stage("Clone code from GitHub") {
            steps {
                script {
                    git url: 'https://github.com/knowledgemate/Maven-Tomcat-Setup.git', branch: 'main'
                }
            }
        }
        stage("Maven Build") {
            steps {
                script {
                    sh "mvn clean package"
                }
            }
        }
        stage('Unit Test') {
            steps {
                sh 'mvn test'
            }
        }
        stage('Integration Test') {
            steps {
                sh 'mvn verify -DskipUnitTests'
            }
        }
        stage('Checkstyle Code Analysis') {
            steps {
                sh 'mvn checkstyle:checkstyle'
            }
            post {
                success {
                    echo 'Generated Analysis Result'
                }
            }
        }
      stage('SonarScanning') {
            steps {
                sh 'mvn sonar:sonar -Dsonar.host.url=http://100.25.221.208:9000 -Dsonar.login=c479124a76b0edba470a78d67414162e8c44b8b9'
            }
			}
        
      stage("Publish to Nexus Repository Manager") {
            steps {
            sh 'mvn clean deploy'
            }
            }
      stage("Deploy it to tomcat") {
            steps {
            sh 'ssh -t -t root@54.85.47.64 -o StrictHostKeyChecking=no "mvn install tomcat7:deploy"'
            }
        }
}
}
