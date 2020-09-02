node{
stage'git checkout'
git 'https://github.com/dkAug15/DevOps-Training.git'

stage 'Code Analysis'
sh 'sudo mvn sonar:sonar -Dsonar.projectKey=xxxxx -Dsonar.organization=xxxxxx -
Dsonar.host.url=https://sonarcloud.io'


stage 'compile'
sh 'mvn compile'

stage 'test'
sh 'mvn test'

stage 'package'
sh 'mvn package'

stage 'archiveArtifacts'
archiveArtifacts 'target/*.war'
}

