pipeline{

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
        
        stage('Test'){
            when {
                TEST true
            }
        }

        stage('Build backend'){
            when {
                BUILD true
            }
            steps{
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${kube-controller}<<eof
                git clone https://github.com/ezzmo/petclinic
                cd spring-petclinic-backend
                ./mvnw spring-boot:run
                docker login -u ${DOCKER_USER} -p ${DOCKER_PASS}
                docker build -t docktermo/backend .
                docker push docktermo/backend
                '''
            }
        }

        stage('Build frontend'){
            when {
                BUILD true
            }
            steps{
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${kube-controller}<<eof
                git clone https://github.com/ezzmo/petclinic
                cd spring-petclinic-frontend
                ./mvnw spring-boot:run 
                docker login -u ${DOCKER_USER} -p ${DOCKER_PASS}
                docker build -t docktermo/frontend .
                docker push docktermo/frontend
                '''
            }
        }
        stage('Deploy'){
            steps{
                sh label: '', script:
                '''
                sshpass -p ${vmpass} ssh -o StrictHostKeyChecking=no ${kube-controller}<<eof
                git clone https://github.com/ezzmo/petclinic
                cd petclinic
                kubectl apply -f ./kubernetes_implementation/
                '''
            }
        }
    }
}
