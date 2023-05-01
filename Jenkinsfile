@Library('sharedlibs') _

 
pipeline {
    agent any
    tools {
        maven "maven"
        jdk 'jdk-11.0.16.8-hotspot'
    }
     
    stages {
        
      
	  stage('git clone') {
            steps {
                 git branch: 'main', url: 'https://github.com/avinash-kumar-iit/DBDeploymentManager.git'
            }
        }
       
		stage ('demo') {
            steps {
                welcome("Avinash Kumar")
				script{
				log.info("shared lib is working....")
			    log.warning("need to upgrade further...")
				}
            }
			
        }

        stage ('Build') {
            steps {
                
               
                bat 'mvn clean package'
         }
        
   
               
    }
    stage ('Sonarqube') {
            steps {
                script {
             scannerHome = tool 'SonarQubeScanner'
                }
               withSonarQubeEnv('SonarQube'){
                bat "mvn sonar:sonar"
               }
         }
        
   
               
    }
            }
           
        }
