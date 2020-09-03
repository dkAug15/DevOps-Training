node{
stage'git checkout'
git 'https://github.com/dkAug15/DevOps-Training.git'

stage 'Code Analysis'
sh 'mvn sonar:sonar -Dsonar.projectKey=dkAug15_DevOps-Training -Dsonar.organization=dkaug15 -Dsonar.host.url=https://sonarcloud.io'


stage 'compile'
sh 'mvn compile'

stage 'test'
sh 'mvn test'

stage 'package'
sh 'mvn package'

stage 'archiveArtifacts'
archiveArtifacts 'target/*.war'
 
stage ('upload .jar to nexus')
sh 'curl -v -u admin:admin123 --upload-file target/*.war http://18.191.208.246:8081/nexus/content/repositories/releases/'

}

node Webserver {
stage ('Download *.war to nexus')
sh 'curl -O http://<ip>:8081/nexus/content/repositories/releases/DevOps-Training.war'

input 'Pipeline has paused and needs your input before proceeding'
stage 'deploy war on WebServer node'
sh 'sudo cp DevOps-Training.war /var/lib/tomcat8/webapps/'  


}

