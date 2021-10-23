pipeline {
     agent any
     stages {
         stage('Compile Stage') {
             steps {
             agent (maven : 'apache-maven-3.5.0') {
                sh 'mvn clean compile'
              }
            }
          }
          stage('Testing Stage') {
             steps {
                 agent (maven : 'apache-maven-3.5.0') {
                     sh 'mvn test'
                  }
                }
               }
               stage('Install Stage') {
                  steps {
                      agent (maven : 'apache-maven-3.5.0') {
                          sh 'mvn install'
                      }
                    }
                  }
                }
              }
