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
        sh "newman run https://api.getpostman.com/collections/10930042-fb0f7e9b-0084-4b88-8443-9c7bb4a01361?apikey=PMAK-5f3adc0545c71700512debc9-9de11c40559a8d850c21793df26126fc37 --environment https://api.getpostman.com/environments/10930042-1175a283-b0c7-4442-8079-28731de9c639?apikey=PMAK-5f3adc0545c71700512debc9-9de11c40559a8d850c21793df26126fc37"
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
