pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -f javademos-master/ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(fingerprint: true, artifacts: '**/target/*.war')
        sh '''mkdir /home/azureuser/gitRepo/buildoutput/${BUILD_NUMBER}
cp /var/lib/jenkins/workspace/javademos_master/javademos-master/ssgsems/target/*.war /home/azureuser/gitRepo/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}