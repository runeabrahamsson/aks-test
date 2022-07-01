get app + pass
az ad sp create-for-rbac --skip-assignment

update terraform.tfvars
terraform init
terraform plan
terraform apply

setup kubectl
az aks get-credentials --resource-group $(terraform output -raw resource_group_name) --name $(terraform output -raw kubernetes_cluster_name)

az aks browse --resource-group $(terraform output -raw resource_group_name) --name $(terraform output -raw kubernetes_cluster_name)

terraform destroy