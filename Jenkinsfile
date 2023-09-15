pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }
   environment {
    SNAP_REPO = 'vprofile-snapshot'
    NEXUS_USER = 'admin'
    NEXUS_PASS = 'test@123'
    RELEASE_REPO = 'vprofile-release'
    CENTRAL_REPO = 'vpro-maven-central'
    NEXUSIP = '54.204.76.81'
    NEXUSPORT = '8081'
    NEXUS_GRP_REPO = 'vpro-maven-group'
    NEXUS_LOGIN = 'nexuslogin'
    NEXUS_PORT = '8081' // Replace with the actual port you want to use
}

   stages {
    stage('Build') {
        steps {
            sh "mvn -s settings.xml -DskipTests -Dusername=${NEXUS_USER} -Dpassword=${NEXUS_PASS} install"
        }
    }
}
}