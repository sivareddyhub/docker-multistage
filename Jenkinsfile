pipeline{
agent any
	

	tools {
    	maven 'maven-3.6.3'
	
    }
	stages{
		stage("build"){
			steps {
				script{
					sh "mvn clean package"
				}
			}
		}
  stage("dynamic-deploy"){
            steps{
                script{
            sshagent(['sracred']) {
	    
	    }
sh "ansible-playbook -i aws_ec2.yaml  tomcat.yml"
                }
            }
	    
        }
        
	}
	}
		

