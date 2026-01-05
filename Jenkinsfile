node {
   
        stage('Clone') {
           
            git branch: 'master', url: 'https://github.com/srinfotechbatch3/onlinebookstore.git'
            }
       
        stage('Build') {
        
               bat 'mvn clean install'
        }

      
        stage('Published Artifacts') {
          
              archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
        
        }

        stage('Deploy to Target Server') {
            
              deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'TomcatCredentials', path: '', url: 'http://localhost:8080/')], contextPath: 'Onlinebookstore', war: 'target/*.war'
            
        }
    }
