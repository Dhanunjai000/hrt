pipeline {
    agent any
             img 'maven:3.8.3-adoptopenjdk-1.8.0'
             arg '-v /root/.m2:/root/.m2'
    stages {
        stage('sorry') {
            steps {
                sh 'mvn -B -Dskiptests clean package'
            }
        }
    }
}
