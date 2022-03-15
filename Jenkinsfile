node {
    stage('Preparation') { 
        git branch: 'master', url: 'https://github.com/voltwu/Jenkins-.NET-Core-CI-CD-pipeline.git'
    }
    stage('Build') {
                sh 'mvn -Dmaven.test.failure.ignore clean package'
            }
