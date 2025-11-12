pipeline {
    agent any
    tools {
        maven "MAVEN3.9"
        jdk "JDK17"
    }
    
    environment {
        SNAP_REPO = 'vprofile-snapshot'
		NEXUS_USER = 'admin'
		NEXUS_PASS = '3151999@!Mo'
		RELEASE_REPO = 'vprofile-release'
		CENTRAL_REPO = 'vpro-maven-central'
		NEXUSIP = '3.95.201.236'
		NEXUSPORT = '8081'
		NEXUS_GRP_REPO = 'vpro-maven-group'
        NEXUS_LOGIN = 'nexuslogin'
    }

    stages {
        stage('Build'){
            steps {
                sh 'mvn -s settings.xml -DskipTests install'
            }
            post{
                success{
                    echo'archiving artifacts ...'
                    archiveArtifacts artifacts: '**/*.war'
                }
            }
        }
        stage('test'){
            steps{
                sh 'mvn test'
            }
        }

        stage('CheckStyle Analysis'){
            steps{
                sh 'mvn checkstyle:checkstyle'
            }   
        }
    }
}