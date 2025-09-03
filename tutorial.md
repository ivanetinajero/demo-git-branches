## 1. Introducción
- **Objetivo del ejercicio:** Aprender a usar Git y GitHub trabajando con ramas y fusiones en un proyecto real usando Visual Studio Code.
- **Qué aprenderás:**
	- Inicializar un repositorio
	- Crear y trabajar con ramas
	- Hacer merges y resolver conflictos
	- Documentar el proceso

## 2. Creación del Repositorio
- Crear un repositorio en GitHub llamado `demo-git-branches` (sin inicializar con README).
- Clonar o inicializar el repositorio localmente:
	```bash
	git init
	git remote add origin <URL-del-repositorio>
	```
- Crear la rama principal y hacer el primer commit:
	```bash
	git checkout -b main
	git add index.html tutorial.md
	git commit -m "Primer commit: estructura base del proyecto"
	git push -u origin main
	```

## 3. Primera Versión de la Landing Page
- Instalar Bootstrap 5 usando CDN en el archivo `index.html`.
- Crear la estructura básica del sitio:
	```html
	<!DOCTYPE html>
	<html lang="es">
	<head>
		<meta charset="UTF-8">
		<meta name="viewport" content="width=device-width, initial-scale=1.0">
		<title>Landing Page Demo</title>
		<!-- Bootstrap 5 CDN -->
		<link href="https://cdn.jsdelivr.net/npm/bootstrap@5.3.8/dist/css/bootstrap.min.css" rel="stylesheet">
	</head>
	<body>
		<div class="container">
			<h1 class="mt-5">Bienvenido a la Landing Page Demo</h1>
			<p class="lead">¡Proyecto de práctica con Git y Bootstrap 5!</p>
		</div>
	</body>
	</html>
	```
- Commit y push:
	```bash
	git add index.html
	git commit -m "Landing page inicial con Bootstrap 5"
	git push
	```

## 4. Trabajo con Ramas

### 4.1. Crear y cambiar de rama
- Crear una nueva rama para cada funcionalidad:
	```bash
	git checkout -b nombre-de-la-rama
	```

### 4.2. Ejercicio práctico por ramas

- **Rama navbar:**
	- Crear la rama:
		```bash
		git checkout -b navbar
		```
	- Agregar el código del navbar en `index.html`.
	- Guardar y hacer commit:
		```bash
		git add index.html
		git commit -m "Agrega navbar de Bootstrap a la landing page"
		git push -u origin navbar
		```
	- Fusionar en main:
		```bash
		git checkout main
		git pull
		git merge navbar
		git push
		```

- **Rama footer:**
	- Crear la rama:
		```bash
		git checkout -b footer
		```
	- Agregar el código del footer en `index.html`.
	- Guardar y hacer commit:
		```bash
		git add index.html
		git commit -m "Agrega footer de Bootstrap a la landing page"
		git push -u origin footer
		```
	- Fusionar en main:
		```bash
		git checkout main
		git pull
		git merge footer
		git push
		```

- **Rama cards:**
	- Crear la rama:
		```bash
		git checkout -b cards
		```
	- Agregar el código de la sección de tarjetas (cards) en `index.html`.
	- Guardar y hacer commit:
		```bash
		git add index.html
		git commit -m "Agrega sección de tarjetas (cards) de Bootstrap"
		git push -u origin cards
		```
	- Fusionar en main:
		```bash
		git checkout main
		git pull
		git merge cards
		git push
		```

- **Rama contacto:**
	- Crear la rama:
		```bash
		git checkout -b contacto
		```
	- Agregar el código del formulario de contacto en `index.html`.
	- Guardar y hacer commit:
		```bash
		git add index.html
		git commit -m "Agrega formulario de contacto de Bootstrap"
		git push -u origin contacto
		```
	- Fusionar en main:
		```bash
		git checkout main
		git pull
		git merge contacto
		git push
		```

## 4.3. Eliminación de ramas después de fusionar

Una vez que una rama de funcionalidad (por ejemplo, `navbar`, `footer` o `cards`) ha sido fusionada exitosamente en la rama principal (`main`), es recomendable eliminarla para mantener el repositorio limpio y organizado.

**Comandos para eliminar una rama:**

- Eliminar la rama localmente:
	```bash
	git branch -d nombre-de-la-rama
	```
- Eliminar la rama en el remoto (GitHub):
	```bash
	git push origin --delete nombre-de-la-rama
	```

Esto no afecta el historial ni los cambios ya fusionados. Es una buena práctica profesional y ayuda a evitar confusiones con ramas antiguas o innecesarias.
