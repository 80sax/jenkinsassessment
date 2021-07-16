pipeline {
  agent none
  tools {
    maven 'my_maven'
  }
  stages {
    parallel {
      stage("Compilation") {
        agent { label "aws1" }
        steps { sh "mvn compile" }
      }
      stage("Testing") {
        agent { label "aws2" }
        steps { sh "mvn test" }
      }
    }
  }
}

