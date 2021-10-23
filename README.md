pipeline {
     agent any
     stages ('Compile Stage') {
        steps {
             withMaven(maven : 'apache-maven-3.8.3') {
                bat 'mvn clean compile'
              }
            }
          }
          stages('Testing Stage') {
             steps {
                 withMaven(maven : 'apache-maven-3.8.3') {
                     bat 'mvn test'
                  }
                }
               }
               stages('Install Stage') {
                  steps {
                      withMaven(maven : 'apache-maven-3.8.3') {
                          bat 'mvn install'
                      }
                    }
                  }
                }
