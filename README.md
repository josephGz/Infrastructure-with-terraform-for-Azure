# Infrastructure-with-terraform-for-Azure
#Iniciar sesión en Azure
az login

#Escoger el Subscription ID de la cuenta Azure de preferencia
az account set --subscription "35akss-subscription-id"

#Crear una entidad de servicio
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<SUBSCRIPTION_ID>"

#Establecer variables de entorno
$ $Env:ARM_CLIENT_ID = "<APPID_VALUE>"
$ $Env:ARM_CLIENT_SECRET = "<PASSWORD_VALUE>"
$ $Env:ARM_SUBSCRIPTION_ID = "<SUBSCRIPTION_ID>"
$ $Env:ARM_TENANT_ID = "<TENANT_VALUE>"

#Iniciar proyecto terraform
terraform init
#Validar configuraciones
terraform validate
#Desplegar las configuraciones
terraform apply -auto-approve
