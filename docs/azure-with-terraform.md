# Azure With Terraform
*Deploying resources on Azure using Terraform from local MacOS*

---
## Terraform
General command
```terraform
terraform init
terraform fmt
terraform validate
terraform plan
terraform plan -out=main.tfplan
terraform apply "main.tfplan"
terraform apply -auto-approve
terraform destroy -auto-approve
```

## Azure

Login to azure from cli:
```
az login
az login --tenant 8c758e1f-324a-4737-bcc3-11b8eba45587
az login -use-device-code
```

Get location information: `az account list-locations --output table`

Available vm size in a location:
```
az vm list-sizes --location eastus --query "[?(numberOfCores == \`2\` && memoryInMB == \`4096\`)].{CPU:numberOfCores, RAM:memoryInMB, Type:name}" -o table
```

User current login: `az account show --output json`
