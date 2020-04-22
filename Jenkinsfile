pipeline{
<<<<<<< HEAD

    agent any
    parameters {
        booleanParam (
            defaultValue: false,
            description: '',
            name: 'TEST')
        booleanParam (
            defaultValue: true,
            description: '',
            name: 'BUILD')
    }
    stages{
        
        stage('Testing'){
            when {
                TEST true
            }
        }

        stage('Build backend jar'){
            when {
                BUILD true
            }
            steps{
                sh label: '', script:
                '''
                cd spring-petclinic-backend
                ./mvnw spring-boot:run
                '''
            }
        }

        stage('Build backend image'){
            when {
                BUILD true
            }
            steps{
                sh label: '', script:
                '''
                docker build -t docktermo/backend .
                '''
            }
        }

        stage('Build frontend image'){
            when {
                BUILD true
            }
            steps{
                sh label: '', script:
                '''
                cd spring-petclinic-frontend
                docker build -t docktermo/frontend .
                '''
            }
        }

        stage('Push images'){
            when {
                BUILD true
            }
            steps{
                sh label: '',
            }
        }
    }
}
=======
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
>>>>>>> 1e6109d0802f55a140d7f9fd99adcccb28c6c61b
