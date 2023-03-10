mvn sonar:sonar -Dsonar.host.url=http://localhost:9000 -Dsonar.login=f5782cfeafd95d3216f992b6c35bbdfe5fd67ac3

mvn clean deploy

mvn install tomcat7:deploy


Jenkins user connectivity:

sudo su -s /bin/bash jenkins

/var/lib/jenkins/.ssh/id_rsa.pub  copy to /root/.ssh/authorized_keys
