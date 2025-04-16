pipeline:
  agent: none
  environment:
    KUBE_CREDENTIAL_ID: "bhtpav3-dev-uat"
  stages:
    - stage: "Deploy CronJob"
      agent:
        kubernetes:
          cloud: "kubernetes"
          namespace: "default"
          credentialsId: "${KUBE_CREDENTIAL_ID}"
          defaultContainer: "kubectl"
          containers:
            - name: "kubectl"
              image: "bitnami/kubectl:latest"
              ttyEnabled: true
              command:
                - "cat"
      steps:
        - script: |
            echo "Applying CronJob YAML to cluster..."
            kubectl config use-context default
            kubectl apply -f ./cronjob.yam