pipeline {
  agent {
    docker {
    image "node:10-alpine"
    args "--network=skynet"
    }
  }
  stages {
     stage ("Build") {
       steps {
         sh "npm install"
         sh "npm install -g newman"
         sh "npm install -g newman-reporter-html"
       }
     }
    stage ("Test"){
      steps {
        sh "newman run link apiPostMan"
      }
     
    }
    stage("Production"){
      steps {
      input message: "Go to production?(Clik 'Proceed' to continue)"
      sh "echo 'Subindo em produção'"
      }
    }
  }
}
