node {
    stage('Preparation') { 
        git 'https://github.com/swap1408/sparkjava-war-example.git'
    }
    stage('Build') {
                sh 'mvn clean package'
            }
    stage('ArchiveResults') {
        archiveArtifacts 'target/*.war'
    }
     
    stage('deploy user') {
         sshagent(['deploy user']) {
             sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tomcat-war/target/sparkjava-hello-world-1.0.war ubuntu@13.126.21.136:/opt/tomcat/webapps/"
        } 
    }
}
