# Trabajo Individual

**Nombre:** Gabriel Bazualdo Rojas  
**Correo:** bazualdogabriel@gmail.com 

## Clase 1
### ¿ Que es Git?

Es un sistema de control de versiones distribuido (VCS), que permite guardar
archivos y sus versiones. 
Esto sirve para no perder información y poder regresar a versiones anteriores
si algo sale mal.

### ¿Como nacio Git?

Fue creado por Linus Torvalds  porque había problemas con otras herramientas,
entonces su decidió hacer su propia solución en para el control de versiones,
la cual le llevo unas 2 a 3 semanas.

### ¿Como instalar git?

Para instalar Git se debe ir a la página oficial https://git-scm.com/install/
y descargarlo según el sistema operativo.

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

- README.md
- .gitignore
---
## Clase 2
### States y Commits
![Imagen graciosa](images/git-commit-funny.png)
### Los Estados de Git
Git tiene 3 estados principales por donde pasan nuestros archivos:

1. **Directorio de Trabajo (Working Directory):** Donde tengo mis archivos 
y los modifico.Git ya sabe que existen, pero los cambios todavía no están 
guardados en el historial.

2. **Área de Preparación (Staging Area):** Es como una zona de espera.Aquí 
pongo los cambios que ya están listos y que quiero incluir en mi próximo commit.

3. **Repositorio Local (Repository):** Una vez que hago commit, los cambios 
que estaban en el Staging Area se guardan de forma permanente en el historial 
de mi proyecto.

![Diagrama de los Estados de Git](images/estados_de_git.png)

### 1. Directorio de Trabajo (Modificado)
Cuando trabajo en mis archivos, Git los ve así:

- **Untracked:** Archivos nuevos que acabo de crear y que Git todavía no sigue.
- **Modified:** Archivos que ya estaban en Git pero que he modificado.

#### ¿Cómo descartar cambios?
Si hice un cambio en un archivo pero me arrepentí y quiero volver a como estaba 
en el último commit, puedo usar:
```
git restore <archivo>
```
> **Ojo:** ¡Esto borra fisicamente los cambios para siempre!

#### Ignorar archivos con `.gitignore`
Para que Git no de seguimiento a  ciertos archivos los añado a un archivo 
llamado .gitignore.

Ejemplo de mi .gitignore:
```
# Directorios y archivos ignorados por Git
venv/
__pycache__/
.env
*.log
```

### 2. Área de Preparación (Staging Area)
Es donde preparo mi siguiente commit, para añadir archivos a esta zona:
- Para añadir un solo archivo
```git add <archivo>```
- Para añadir todos los archivos nuevos y modificados
```git add .```

Si me equivoqué y quiero sacar un archivo del Staging Area:
```git restore --staged <archivo>```

### 3. Repositorio Local (Confirmado)
Es la ultima fase, los cambios se guardan en el historial.
- Para crear el commit:
```git commit -m "Un mensaje que explique qué hice"```
- Si quiero deshacer el último commit:
```git reset --soft HEAD~1```

### Buenas Prácticas para Commits
**Commits Atómicos**  
La idea es que cada commit sea un cambio pequeño y único.Es mejor hacer 
varios commits pequeños que uno grande con un montón de cambios mezclados.  
**Escribir buenos commits**  
Deben describir lo que hacen en pocas palabras:

1. Usar verbos en imperativo: Empezar el mensaje con Add, Change, Fix, Remove.
2. Sin punto al final ni puntos suspensivos.
3. Máximo 50 caracteres en el título.
4. Usar prefijos: Ayuda a saber de qué va el commit a simple vista.

	```git commit -m "<tipo de commit>: <descripción>"```
	
	Ejemplo:
	
	```git commit -m "feat: Add new search feature"```

	Los prefijos más comunes:

	- feat: Una funcionalidad nueva.
	- fix: Arreglar un error (bug).
	- perf: Un cambio para mejorar el rendimiento.
	- docs: Cambios en la documentación.
	- style: Cambios de formato (espacios, comas, etc.).
	- refactor: Reorganizar código sin cambiar lo que hace.
	- test: Añadir o arreglar tests.
	- build: Cambios que afectan el sistema de build.
	- ci: Cambios en la integracion continua

5. Añadir más detalles si es necesario en el cuerpo del commit: 
Si el título no es suficiente, puedo usar ```git commit```
(sin -m) para escribir un cuerpo más largo.
```
prefijo: Titulo de tu commit

Cuerpo que describe tu commit
```
---

