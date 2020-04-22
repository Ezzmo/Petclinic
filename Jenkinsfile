pipeline{
        agent any

	stages{
	     
	     stage('Testing Pet Clinic Application'){
                steps{
		    
	            sh label: '', script: '''
                        sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${kube-controller}<<eof
			
		'''
                }
            } 	
	    	
            stage('Stack Deploy on Manager VM'){
                steps{
		    
	            sh label: '', script: '''
                        sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${kube-controller}<<eof
			
			
		'''
                }
            }
        }    
}
