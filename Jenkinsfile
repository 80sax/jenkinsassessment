pipeline {
  agent none
  tools { maven 'my_maven' }
  stages {
    stage("Build") {
      parallel {
        stage("Testing") {
          agent { label "aws2" }
          steps { sh "mvn test" }
        } 
        stage("Compilation") {
          agent { label "aws1" }
          steps { sh "mvn compile" }
        }
      }
    }
  }
}

