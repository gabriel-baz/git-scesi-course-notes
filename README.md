# Trabajo Individual

**Nombre:** Gabriel Bazualdo Rojas  
**Correo:** bazualdogabriel@gmail.com 

## Clase 1
### ¿ Que es Git?

Es un sistema de control de versiones distribuido (VCS), que permite guardar archivos y sus versiones. 
Esto sirve para no perder información y poder regresar a versiones anteriores si algo sale mal.

### ¿Como nacio Git?

Fue creado por Linus Torvalds  porque había problemas con otras herramientas,
entonces su decidió hacer su propia solución en para el control de versiones, la cual le llevo unas 2 a 3 semanas.

### ¿Como instalar git?

Para instalar Git se debe ir a la página oficial https://git-scm.com/install/ y descargarlo según el sistema operativo.

Después de instalarlo, se puede verificar con el siguiente comando en la terminal:
```
git --version
```
Si muestra la versión, significa que está bien instalado.

### Configuraciones Básica

Después de instalar Git, es necesario configurarlo con nuestros datos:
```
git config --global user.name "Tu Nombre"

git config --global user.email "tu@correo.com"

git config --global core.autocrlf true
```
Esto sirve para identificar quién hace los cambios en el repositorio.

### Achivos que todo repo deberia tener

-README.md
-.gitignore

---
