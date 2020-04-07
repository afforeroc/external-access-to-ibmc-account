# External access to an IBM Cloud main account
Tutorial to learn how to access externally to an IBM Cloud main account.

## Guía para dar acceso a infraestructura desde una cuenta principal a una externa
Caso ejemplo de Kubernetes de IBM Cloud

1. En el panel superior de IBM Cloud seleccionar: 
Gestionar -> Cuentas -> Usuarios

2. Dentro del menú de Usuarios, presionamos el botón “Invitar a usuarios” y escribimos los correos con cuenta de IBM Cloud.

3. Seleccionamos los tipos de accesos
a. Servicios
b. Acceso a Cloud Foundry
c. Acceso a Infraestructura (para cuentas que tienen SoftLayer)

4. Enviamos las invitaciones a los correos y verificamos que sea correcto.

5. Para habilitar acceso a la infraestructura, iniciamos la ventana de comandos de tu sistema operativo como CMD, PowerShell o Terminal con permisos de super usuario o administrador.

6.	
a. Inicie sesión en el terminal como propietario de la cuenta.
```
ibmcloud login [--sso]
```

b. Dirígete al grupo de recursos en el que deseas establecer la clave API. Si no se dirige a un grupo de recursos, la clave API se establece para el grupo de recursos ‘Default’.
```
ibmcloud target -g <resource_group_name>
```
```
ibmcloud target -g Default
```

c. Si está en una región diferente, cambie a la región donde desea configurar la clave API.
```
ibmcloud ks region-set
```

d. Establezca la clave API para la región y el grupo de recursos.
```
ibmcloud ks api-key-reset
```

e. Verifique que la clave API esté establecida.
```
ibmcloud ks api-key-info <cluster_name_or_ID>
```