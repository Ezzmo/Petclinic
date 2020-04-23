pipeline{
    agent any
    parameters {
        booleanParam (
            defaultValue: true,
            description: '',
            name: 'TEST')
        booleanParam (
            defaultValue: true,
            description: '',
            name: 'BUILD')
        booleanParam (
            defaultValue: true,
            description: '',
            name: 'DEPLOY')
    }
    stages{
        
        stage('Test backend'){
            when {
                expression { params.TEST == true }
            }
            steps {
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -T -o StrictHostKeyChecking=no ${kube}<<eof
                rm -rf petclinic
                git clone https://github.com/ezzmo/petclinic
                cd petclinic
                cd spring-petclinic-backend
                mvn test
                '''
            }
        }
        stage('Test frontend'){
            when {
                expression { params.TEST == true }
            }
            steps {
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -T -o StrictHostKeyChecking=no ${kube}<<eof
                rm -rf petclinic
                git clone https://github.com/ezzmo/petclinic
                cd petclinic
                cd spring-petclinic-frontend
                ls -al
                npm install
                npm test
                '''
            }
        }

        stage('Build frontend'){
            when {
                expression { params.BUILD == true }
            }
            steps{
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -T -o StrictHostKeyChecking=no ${kube}<<eof
                git clone https://github.com/ezzmo/petclinic
                cd petclinic
                cd spring-petclinic-frontend
                docker login -u ${DOCKER_USER} -p ${DOCKER_PASS}
                docker build -t docktermo/frontend .
                docker push docktermo/frontend
                '''
            }
        }
        stage('Deploy'){
            when {
                expression { params.DEPLOY == true }
            }
            steps{
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -T -o StrictHostKeyChecking=no ${kube}<<eof
                rm -rf petclinic
                git clone https://github.com/ezzmo/petclinic
                cd petclinic
                kubectl apply -f kubernetes_implementation/
                sleep 60s
                kubectl get svc
                '''
            }
        }
    }
}
