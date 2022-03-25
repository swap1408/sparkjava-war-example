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
             sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tomcat/target/sparkjava-hello-world-1.0.war ubuntu@15.206.124.180:/opt/tomcat/webapps/"
        } 
    }
}
