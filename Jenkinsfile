#!groovy
//  groovy Jenkinsfile
properties([disableConcurrentBuilds()])\

pipeline  {
        agent { 
           label ''
        }

    options {
        buildDiscarder(logRotator(numToKeepStr: '10', artifactNumToKeepStr: '10'))
        timestamps()
    }
    stages {
        stage("Git clone") {
            steps {
                sh '''
                cd /home/got/
                git clone  https://github.com/olegstepit/zabbix.git           
                '''
            }
        }    
        stage("Work") {
            steps {
                sh '''
                cd /home/got/zabbix
                docker-compose up -d
                '''
            }
        }   
    }
}
