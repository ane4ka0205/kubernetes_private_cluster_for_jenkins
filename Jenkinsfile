pipeline{
    agent any
        stages{
            stage("Pull repo"){
                steps{
                    git 'https://github.com/ane4ka0205/terraform.git'
                }
            }
            stage("Terraform init"){
                steps{
                    ws("${workspace}/dev/kubernetes_cluster_private"){
                        sh "terraform init"
                    }
                }
            }
            stage("Terraform apply"){
                steps{
                    ws("${workspace}/dev/kubernetes_cluster_private"){
                        sh "terraform ${action} -auto-approve"
                }
            }
        }
    }
}
