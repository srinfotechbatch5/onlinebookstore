pipeline{
    
    
    stages{
        
        stage('clone'){
            
            steps{
                git branch: 'feature/2026.01.26', url: 'https://github.com/srinfotechbatch5/onlinebookstore.git'
                
            }
        }
        stage('Build'){
            
            steps{
             bat 'mvn install'
                
            }
        }

        stage('Test'){
            
            steps{
             bat 'mvn test'
                
            }
        }

        stage('Generated Artifacts'){
            
            steps{
           archiveArtifacts artifacts: 'target/*.war', followSymlinks: false
                
            }
        }

         stage('Deploy'){
            
            steps{
          
		  deploy adapters: [tomcat9(alternativeDeploymentContext: '', credentialsId: 'TomcatCredentials', path: '', url: 'http://localhost:8080/')], contextPath: 'SRINFOETCHONLINEBOOKSTOREApplication', war: 'target/*.war'
                
            }
        }
    }
}