pipeline {
    agent any
    docker 
    {
             pull image 'maven:3.8.3-adoptopenjdk-1.8.0'
             args '-v /root/.m2:/root/.m2'
             }
    stages {
        stage('sorry')
        {
            steps {
                sh 'mvn -B -Dskiptests clean package'
            }
        }
    }
}
