pipeline {
   agent { 
    node  {
      lable 'docker'
      }
    }
    options {
         timestamps()
    }
    
    environment  {
       IMAGE = readMavenPom().getArtifactId()
       VERSION = readMavenPom().getVersion()
    }
  }
