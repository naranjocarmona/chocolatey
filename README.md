# ¿Qué es chocolatey?
Es un gestor de paquetes para Windows. 

Desplegar software puede ser repetitivo, complejo y propenso a errores. Chocolatey simplifica la instalación de software automatizando la descarga de todos los paquetes necesarios y sus dependencias.

# Instalación de chocolatey
Se puede instalar en múltiples entornos, incluidos algunos utilizados en DevOps como [Ansible](https://es.wikipedia.org/wiki/Ansible_(software)) o [Chef](https://es.frwiki.wiki/wiki/Chef_%28logiciel%29) para la integración, desarrollo y despliegue continuo.

Dependiendo del entorno, el método de instalación es diferente, pero en este caso interesa explicar cómo instalar Chocolatey para uso individual en un PC.

## Instalación en un PC
En ambas opciones hay que abrir PowerShell con permisos de administrador.
> Opción 1

Chocolatey se instala mediante un script de PowerShell (extensión .ps1). Se puede encontrar en la carpeta `scripts` de este repositorio.

Antes de ejecutarlo, hay que asegurarse de que el comando `Get-ExecutionPolicy` no muestra `Restricted`.

De ser así, habrá que ejecutar:
```
Set-ExecutionPolicy Unrestricted
```
y finalmente ejecutar el script `install.ps1`
> Opción 2

De forma alternativa, simplemente se puede ejecutar lo siguiente:

```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://community.chocolatey.org/install.ps1'))
```
Este último comando lo hace todo en uno. Establece la regla de ejecución y descarga e instala el script.

# Ejemplos de instalación
Puede que haya que cerrar y abrir de nuevo PowerShell después de instalar Chocolatey.

Para buscar paquetes que se pueden instalar se puede visitar la página [https://community.chocolatey.org/packages](https://community.chocolatey.org/packages)

Tiene un buscador y aparece el comando exacto a ejecutar en PowerShell.

Se ejecuta y comienza la instalación:


Una vez finalizado, se comprueba que ha instalado el software, en este caso Adobe Acrobat Reader.

Finalmente, para actualizar el software instalado con Chocolatey, se puede ejecutar:
```
choco upgrade all
```


# Referencias

[Página oficial de Chocolatey](https://chocolatey.org)

[Paquetes para instalar](https://community.chocolatey.org/packages)

[Script de instalación](https://community.chocolatey.org/install.ps1)

[Ansible - Wikipedia](https://es.wikipedia.org/wiki/Ansible_(software))

[Chef - frwiki](https://es.frwiki.wiki/wiki/Chef_%28logiciel%29)
