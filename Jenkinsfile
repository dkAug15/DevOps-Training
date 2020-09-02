node{
stage'git checkout'
git 'https://github.com/dkAug15/DevOps-Training.git'

stage 'compile'
sh 'mvn compile'

stage 'test'
sh 'mvn test'

stage 'package'
sh 'mvn package'

stage 'archiveArtifacts'
archiveArtifacts 'target/*.war'
}

