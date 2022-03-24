node {
    stage('Preparation') { 
        git 'https://github.com/adhavvishal/sparkjava-war-example.git'
    }
    stage('Build') {
                sh 'mvn clean package'
            }
    stage('ArchiveResults') {
        archiveArtifacts 'target/*.war'
    }
     /*stage('ArchiveToNexus') {
        nexusArtifactUploader artifacts: [[artifactId: 'MyHelloWorldWebapp', classifier: '', file: 'target/sparkjava-hello-world-1.0.war', type: 'war']], credentialsId: 'nexus', groupId: 'MyHelloWorldWebapp', nexusUrl: '172.31.83.216:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0-SNAPSHOT'
    } */
    stage('Deploy-War') {
         sshagent(['deploy-war']) {
             sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/java-project1/sparkjava-hello-world-1.0.war ec2-user@54.144.94.207:/var/lib/tomcat9/webapps"
        }
    } 
}
