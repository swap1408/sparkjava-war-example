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
     
    stage('Deploy-War') {
         sshagent(['deploy-war']) {
             sh "scp -o StrictHostKeyChecking=no /var/lib/jenkins/workspace/tomcat-war/target/sparkjava-hello-world-1.0.war ec2-user@54.144.94.207:/opt/apache-tomcat-9.0.60/webapps/"
        } 
    }
}
    
