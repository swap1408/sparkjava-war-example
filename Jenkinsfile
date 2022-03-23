node {
    stage('Preparation') { 
        git branch: 'master', url: 'https://github.com/saaaneo/sparkjava-war-example.git'
    }
    stage('Build') {
                sh 'mvn clean package'
            }
    stage('ArchiveResults') {
        archiveArtifacts 'target/*.war'
    }
     /*stage('ArchiveToNexus') {
        nexusArtifactUploader artifacts: [[artifactId: 'MyHelloWorldWebapp', classifier: '', file: 'target/sparkjava-hello-world-1.0.war', type: 'war']], credentialsId: 'nexus', groupId: 'MyHelloWorldWebapp', nexusUrl: '172.31.83.216:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0-SNAPSHOT'
    } 
    stage('deploy War') {
         sshagent(credentials: ['ubuntu_user']) {
             sh "scp -o StrictHostKeyChecking=no target/sparkjava-hello-world-1.0.war ubuntu@3.92.2.158:/var/lib/tomcat9/webapps"
        }
    } */
}
