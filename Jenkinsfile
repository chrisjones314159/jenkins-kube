pipeline {
    agent any
        stages {
            stage("k8s") {
                steps{
                    withKubeCredentials(kubectlCredentials: [[caCertificate: '', clusterName: 'cluster', contextName: '', credentialsId: 'kube', namespace: 'default', serverUrl: 'https://99FAD5F69307EB20A6C6B0AB59C6D8CA.sk1.eu-west-2.eks.amazonaws.com']])
                
                {
                    
                    sh 'curl -LO "https://storage.googleapis.com/kubernetes-release/release/v1.20.5/bin/linux/amd64/kubectl"'
                    sh 'chmod u+x ./kubectl'
                    sh './kubectl get nodes'
                    sh './kubectl create -f nginx-pod.yml'
                    sh './kubectl create -f nginx-service.yml'
                    sh './kubectl get pods'
                    sh './kubectl get svc'
                
                }

            }
            
            }    
            
        }
}