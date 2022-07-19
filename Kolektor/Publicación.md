# Publicar una librería

**Pasos:**
1. Mergear las ramas donde se ralizaron los cambios a develop, eliminando simpre la rama source.

2. Actualizar el CHANGELOG.md desde la rama develop siguiendo el formato establecido:
	   - formato: https://keepachangelog.com/en/1.0.0
	   - semántica: https://semver.org/spec/v2.0.0.html
	
3. Hacer el commit del changelog de la siguiente manera:
   `git commit "CHANGELOG v1.0.0"`  *(Reemplazar con la versión correspondiente)*
   
4. Script:
	1. Ejecutar en una terminal de git(_gitBash_) el script dependiendo que tipo de cambio es que se publica:
	   - Fixes/Update : `bash -e change_version_and_publish.sh --version=patch`
	   - Changes: `bash -e change_version_and_publish.sh --version=minor`
	   - Breaking changes: `bash -e change_version_and_publish.sh --version=mayor`
	
	2. Cuando pida tus datos, colocar:
		**User: CUIL
		Password: CUIL
		Email: Cualquiera**
	
	_Nota: recordar estar en la rama develop al correr el script_ y en la raiz del proyecto, ya que ahi se encuentra el script.
	![[Pasted image 20220627160321.png]]

   