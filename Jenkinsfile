pipeline{
        agent any

	stages{
	     
	     stage('Testing Pet Clinic Application'){
                steps{
		    
	            sh label: '', script: '''
                        sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${vmuser}<<eof
			
		'''
                }
            } 	
	    	
            stage('Stack Deploy on Manager VM'){
                steps{
		    
	            sh label: '', script: '''
                        sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${vmuser}<<eof
			
			
		'''
                }
            }
        }    
}
