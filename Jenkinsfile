node {
   
        stage('Clone') {
           
            git branch: 'master', url: 'https://github.com/srinfotechbatch3/onlinebookstore.git'
            }
       
        stage('Build') {
        
               bat 'mvn clean install'
        }

   
        stage('Deploy to Target Server') {
            
              deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'TomcatCredentials', path: '', url: 'http://localhost:8080/')], contextPath: 'Onlinebookstore', war: 'target/*.war'
            
        }
    }
