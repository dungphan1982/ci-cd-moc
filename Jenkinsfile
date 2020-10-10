node {
   stage('Preparation') { // for display purposes
      
      git 'https://github.com/mrdung2016/ci-cd-moc.git'          
   }
   stage('Build') {
      sh '/usr/share/maven/bin/mvn -f /var/lib/jenkins/workspace/jenkins-pipeline/gs-spring-boot-master/pom.xml clean install'
   }
   stage('copy artifact') {
      sh '/usr/bin/ansible-playbook /var/lib/jenkins/workspace/jenkins-pipeline/copyFile.yml'
   }
   stage('deploy') {
      // Run shell command
      sh '/usr/bin/ansible-playbook /var/lib/jenkins/workspace/jenkins-pipeline/deploy.yml'
   }
} 