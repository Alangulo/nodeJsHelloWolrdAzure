pipeline {
  agent any
    
  tools {nodejs "node"}
    
  stages {
        
    stage('Cloning Git') {
      steps {
        git 'https://github.com/gustavoapolinario/node-todo-frontend'
      }
    }
        
    stage('Install dependencies') {
      steps {
        sh 'npm install'
      }
    }
     
    stage('Deploy') {
      steps {
         sh 'npm test'
        echo "I am in deploy"

      azureWebAppPublish azureCredentialsId: "alejandrSPJenkins",

      resourceGroup: "alanguloNodeJs", appName: "AlanguloNodeJS", filePath: "**/myAppFiles.zip"

      cleanWs()
      }
    }      
  }
}




