# Infrastructure-with-terraform-for-Azure
#Iniciar sesión en Azure
```bash
az login
```

#Escoger el Subscription ID de la cuenta Azure de preferencia
```bash
az account set --subscription "35akss-subscription-id"
```
#Crear una entidad de servicio
```bash
az ad sp create-for-rbac --role="Contributor" --scopes="/subscriptions/<SUBSCRIPTION_ID>"
```
#Establecer variables de entorno
```bash
$ $Env:ARM_CLIENT_ID = "<APPID_VALUE>"
$ $Env:ARM_CLIENT_SECRET = "<PASSWORD_VALUE>"
$ $Env:ARM_SUBSCRIPTION_ID = "<SUBSCRIPTION_ID>"
$ $Env:ARM_TENANT_ID = "<TENANT_VALUE>"
```


#Iniciar proyecto terraform
```bash
terraform init
```
#Validar configuraciones
```bash
terraform validate
```
#Desplegar las configuraciones
```bash
terraform apply -auto-approve
```
