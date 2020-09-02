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
}

