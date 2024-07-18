pipeline {
    agent any
    tools {
        maven "MAVEN3"
        jdk "OracleJDK8"
    }

    environment {
        SNAP_REPO = 'vprofile-snapshot'
        NEXUS_USER = 'admin'
        NEXUS_PASS = 'admin123'
        RELEASE_REPO = 'vprofile-release'
        CENTRAL_REPO = 'vpro-maven-central'
        NEXUSIP = '172.31.4.107'
        NEXUSPORT = '8081'
        NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }
    
    stages {
        stage('Build') {
            steps {
                withEnv([
                    "SNAP_REPO=${env.SNAP_REPO}",
                    "NEXUS_USER=${env.NEXUS_USER}",
                    "NEXUS_PASS=${env.NEXUS_PASS}",
                    "RELEASE_REPO=${env.RELEASE_REPO}",
                    "CENTRAL_REPO=${env.CENTRAL_REPO}",
                    "NEXUSIP=${env.NEXUSIP}",
                    "NEXUSPORT=${env.NEXUSPORT}",
                    "NEXUS_GRP_REPO=${env.NEXUS_GRP_REPO}"
                ]) {
                    sh 'mvn -s settings.xml -DskipTests install'
                }
            }
        }
    }
}