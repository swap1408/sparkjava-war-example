node {
    stage('Preparation') { 
        git branch: 'master', url: 'https://github.com/saaaneo/sparkjava-war-example.git'
    }
    stage('Build') {
                sh 'm36 clean package'
            }
    stage('ArchiveResults') {
        archiveArtifacts 'target/*.war'
    }
     stage('ArchiveToNexus') {
        nexusArtifactUploader artifacts: [[artifactId: 'MyHelloWorldWebapp', classifier: '', file: 'target/*.war', type: 'war']], credentialsId: 'nexus', groupId: 'MyHelloWorldWebapp', nexusUrl: 'ec2-44-201-204-87.compute-1.amazonaws.com:8081', nexusVersion: 'nexus3', protocol: 'http', repository: 'maven-snapshots', version: '1.0-SNAPSHOT'
    }
}
