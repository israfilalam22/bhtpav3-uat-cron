pipeline {
    agent any

    environment {
        KUBECONFIG_CREDENTIAL_ID = 'bhtpav3-dev-uat'
    }

    stages {
        stage('Deploy CronJob') {
            steps {
                withCredentials([file(credentialsId: "${KUBECONFIG_CREDENTIAL_ID}", variable: 'KUBECONFIG')]) {
                    sh '''
                        kubectl --kubeconfig=$KUBECONFIG apply -f cronjob.yaml
                    '''
                }
            }
        }
    }
}
