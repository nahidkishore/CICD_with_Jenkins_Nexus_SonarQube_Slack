pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }


environment {
    SNAP_REPO = 'vprofile-snapshot'
    NEXUS_USER = 'admin'
    NEXUS_PASS = 'admin'
    RELEASE_REPO = 'vprofile-release'
    CENTRAL_REPO = 'vpro-maven-central'
    NEXUS_IP = '54.204.76.81' // Define NEXUS_IP here
    NEXUS_PORT = '8081'
    NEXUS_GRP_REPO = 'vpro-maven-group'
    NEXUS_LOGIN = 'nexuslogin'
}


   stages {
    stage('Build'){
              steps {
                  sh 'mvn -s settings.xml -DskipTests install'
              }
              post {
                  success {
                      echo "Now Archiving."
                      archiveArtifacts artifacts: '**/*.war'
                  }
              }
          }

}
}