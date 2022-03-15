node {
    stage('Preparation') { 
        git branch: 'master', url: 'https://github.com/saaaneo/sparkjava-war-example.git'
    }
    stage('Build') {
                sh 'mvn -Dmaven.test.failure.ignore clean package'
            }
    stage('ArchiveResults') {
        archiveArtifacts 'target/*.war'
    }
}
