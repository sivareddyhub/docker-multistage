pipeline{
agent any
	environment{
	
	AWS_CREDS = credentials('aws-manage')
	AWS_ACCESS_KEY_ID     = "${env.AWS_CREDS_USR}" 
	AWS_SECRET_ACCESS_KEY = "${env.AWS_CREDS_PSW}"
	
}

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
		  sshagent(['keyname']) {
                   sh "ansible-playbook -i aws_ec2.yaml tomcat.yml"

                }
            }
  } 
        }
        
}	
	
		

