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

Servidor Moodle
Otorgamos permiso al script para ejecutarlo.
```bash
sudo chmod 775 moodle.sh
./moodle.sh
```
Una vez que termine de ejecutar el script, se abrirá el archivo php.ini y se modificará. Buscar la linea:
```bash
;max_input_vars = 1000
max_input_vars = 10000
```
Accedemos a nuestro portal de instalación de moodle: [Instalación Moodle](http://moodle-server.eastus.cloudapp.azure.com)

Servidor Drupal
Otorgamos permiso al script para ejecutarlo.
```bash
sudo chmod 775 drupal.sh
./drupal.sh
```
Creamos la siguiente extensión en nuestra base de datos.
```bash
CREATE EXTENSION pg_trgm;
```
Ahora que finalizo de ejecutarse el script, añadimos la siguientes lineas al archivo drupal.conf

```bash
Alias /drupal /var/www/html/azuredrupal
<Directory /var/www/html/azuredrupal>
        Require all granted
        AllowOverride All
</Directory>
```
