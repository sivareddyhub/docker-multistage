pipeline{
agent any
	

	tools {
    	maven 'maven-3.6.3'
	
    }
	stages{
		stage("build"){
			steps {
			sh "mvn clean package"
				}
			}
		
  stage("dynamic-deploy"){
            steps{
                
            sshagent(['sracred']) {
	    
	    
sh "ansible-playbook  tomcat.yml ansible_user=ec2-user "
                }
            }
  } 
        }
        
	}
	
		

