pipeline {
   agentany { 
   stages(docker){
       stage(Build)
    }
    options {
         timestamps()
    }
    
    environment  {
       IMAGE = readMavenPom().getArtifactId()
       VERSION = readMavenPom().getVersion()
    }
  }
}
