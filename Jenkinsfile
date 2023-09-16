pipeline {
    agent { label 'jenkins-agent' }
    tools {
      jdk 'java17'
      maven 'maven3'
    }
  
  stages { 
    stage ("Cleanup Workspace") {
      steps {
          CleanWs()
        }
    }

    stage ("Checkout from SCM") {
      steps {
        git branch: 'main' , credentialsID: 'github' , url: 'https://github.com/Shreedeepa/registration-app.git'
      }
    }

    stage ("Build Application") {
      steps {
        sh "mvn clean package"
      }
    }

    stage ("Test Application") {
      steps {
        sh "mvn test"
      }
    }
  }
}
