
# Tutorial: Aprendiendo Git con un Proyecto Real (Landing Page con Bootstrap 5)

## 1. Introducción

Este tutorial te guiará paso a paso para aprender Git y GitHub usando Visual Studio Code, aplicando buenas prácticas de trabajo con ramas, fusiones y resolución de conflictos en un proyecto real: una landing page con Bootstrap 5.

### Objetivo del ejercicio
- Aprender a usar Git y GitHub trabajando con ramas y fusiones en un proyecto real usando Visual Studio Code.

### Qué aprenderás
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

## 4. Trabajo con Ramas y Funcionalidades

### 4.1. Crear y cambiar de rama
- Crear una nueva rama para cada funcionalidad:
	```bash
	git checkout -b nombre-de-la-rama
	```

### 4.2. Ejercicios prácticos por ramas

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

### 4.3. Eliminación de ramas después de fusionar

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

## 5. Resolución de conflictos de merge

### 5.1 ¿Cómo se provoca un conflicto?

Un conflicto de merge ocurre cuando dos ramas modifican la misma línea de un archivo de forma diferente. Por ejemplo, si en la rama `main` y en la rama `cards` se edita el mismo título en `index.html` y luego se intenta fusionar, Git no sabe cuál versión conservar y marca el conflicto.

### 5.2 ¿Cómo se ve un conflicto?

Al hacer el merge, Git inserta marcas especiales en el archivo afectado:

```
<<<<<<< HEAD
<línea o bloque de la rama actual>
=======
<línea o bloque de la rama que se está fusionando>
>>>>>>> nombre-de-la-rama
```

- `<<<<<<< HEAD`: Indica el inicio de la sección en conflicto, mostrando el contenido de la rama actual (por ejemplo, main).
- `=======`: Separa los cambios de ambas ramas.
- `>>>>>>> nombre-de-la-rama`: Indica el final del conflicto y muestra el nombre de la rama que se está fusionando (por ejemplo, cards).

### 5.3 ¿Cómo se resuelve?

1. Abre el archivo con conflicto (por ejemplo, `index.html`).
2. Elige el contenido que deseas conservar (puedes combinar ambos si lo prefieres) y elimina las marcas `<<<<<<<`, `=======`, `>>>>>>>`.
3. Guarda el archivo.
4. Marca el conflicto como resuelto y haz commit:
	```bash
	git add index.html
	git commit -m "Resuelve conflicto de merge entre main y cards"
	```
5. Sube los cambios:
	```bash
	git push
	```

Así se resuelven los conflictos y se continúa con el flujo de trabajo en Git.

### 5.4 Resolución de conflictos múltiples
---

## 6. Recomendaciones finales

- Trabaja siempre en ramas para cada nueva funcionalidad o mejora.
- Haz commits descriptivos y frecuentes.
- Elimina ramas que ya no uses después de fusionarlas.
- Haz pull antes de mergear para evitar conflictos innecesarios.
- Si surge un conflicto, léelo con calma, elige el contenido correcto y documenta la solución.
- Mantén tu documentación (como este tutorial) actualizada para futuras referencias.

¡Felicidades! Ahora tienes una base sólida para trabajar con Git y GitHub en proyectos reales.

También pueden ocurrir conflictos en varias líneas o secciones de un archivo al mismo tiempo. Por ejemplo, si en la rama `main` y en la rama `footer` se editan tanto el título principal como el texto del footer, al hacer merge aparecerán varias zonas de conflicto en el archivo:

```
<<<<<<< HEAD
<línea o bloque de la rama actual>
=======
<línea o bloque de la rama que se está fusionando>
>>>>>>> nombre-de-la-rama
```

Debes revisar cada zona de conflicto, elegir el contenido que deseas conservar (puedes combinar ambos si lo prefieres) y eliminar todas las marcas `<<<<<<<`, `=======`, `>>>>>>>`.

Por ejemplo, puedes dejar:

```html
<h1 class="mt-5">Landing Page con Cambios en Main y Footer Personalizado</h1>
...
<p class="mb-0">&copy; 2025 DemoGit. Footer combinado de main y footer.</p>
```

Después, guarda el archivo, marca el conflicto como resuelto y haz commit:

```bash
git add index.html
git commit -m "Resuelve conflictos múltiples entre main y footer"
git push
```

Así se resuelven conflictos en varias secciones al mismo tiempo.