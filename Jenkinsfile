pipeline {
  agent any
  stages {
    stage('Build') {
      steps {
        sh 'mvn -f javademos/ssgsems/pom.xml -B -DskipTests clean package'
        archiveArtifacts(fingerprint: true, artifacts: '**/target/*.war')
        sh '''mkdir /home/subodh/buildoutput/${BUILD_NUMBER}
cp **/target/*.war /home/azureuser/gitRepo/buildoutput/${BUILD_NUMBER}'''
      }
    }

  }
}