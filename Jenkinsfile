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

	 sh "ansible-playbook playbook.yml --extra-vars ansible_ssh_user=ec2-user ansible_ssh_pass=Devops@123"
                }
            }
  } 
        }
        
	
	
		

