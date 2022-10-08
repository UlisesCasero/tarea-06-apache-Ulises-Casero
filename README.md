# apache

Reemplace `$ALUMNO` por el nombre de su nombre de usuario en www.tecnologoinformatico.com

EJ: `dmascheroni`

1. Cree el directorio ~/repositorios y dentro clone el
repositorio: `https://github.com/TecnologoInformatico/AdmInf-web.git`

  mkdir ~/repositorios --> crea repositorio en direción indicada
  git clone ~/repositorio/https://github.com/TecnologoInformatico/AdmInf-web.git --> clona el repositorio en la dirección ~/repositorio

2. Actualice el repositorio de la lista de paquetes.
    `apt update`
  
  sudo apt update --> actualiza repositorio

3. Instalar el servidor Apache mediante apt.

  sudo apt install apache2 --> instala servidor Apache

4. Cree el directorio /var/www/$ALUMNO

  sudo mkdir /var/www/ucasero

5. Asigne como propietario del directorio su usuario.

  chown ubuntu /var/www/ucasero

6. Configure un nuevo Virtual host. (copiando el archivo de configuración por defecto)
  
  6.1. ServerName $ALUMNO.tecnologoinformatico.com
     ServerName www.ucasero.tecnologoinformatico.com
  6.2. Correo de contacto con el administrador.
     
  6.3. El root de la aplicación. (/var/www/$ALUMNO)
     DocumentRoot /var/www/ucasero


7. Modifique el archivo /etc/hosts de modo que el ServerName coincida con este equipo `127.0.0.1`.
  
  cd /etc
  sudo vim hosts (modifico agregando 127.0.0.1 www.ucasero.tecnologoinformatico.com,  esc + :w y :q)

8. Reinicie el servidor apache para que los cambios tengan efecto.

  sudo service apache2 restart

9. Copie el contenido del directorio ~/repositorios/AdmInf-web a /var/www/$ALUMNO, de tal modo que el contenido del repositorio antes clonado se encuentre en el root de la aplicación.
  
  cd ~ --> me muevo a home primero
  sudo cp -r AdmInf-web /var/www/ucasero

10. Verifique que el servidor funcione correctamente.

  ingreso la ip 144.22.198.145 en el navegador para compobar su funcionamiento

11. Ingrese la IP del servidor y el servername a continuación:

```json
{
    "serverName": "instancia-infra",
    "ip": "144.22.198.145"
}
```
