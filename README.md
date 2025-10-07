# Universidad [Nombre de la Universidad]  
## Facultad de [Nombre de la Facultad]  
### Carrera de Ingeniería en Software  

**Asignatura:** Manejo y Configuración de Software  
**Nombre del Estudiante:** Jimmy Añilema  
**Fecha:** 7/10/2025

---

# Evaluación Práctica de Git y GitHub

## Instrucciones Generales

- Cada pregunta debe ser respondida directamente en este archivo **(README.md)** debajo del enunciado correspondiente.
- Cada respuesta debe ir acompañada de uno o más **commits**, según se indique en cada pregunta.
- Cuando se indique, deberán realizarse acciones prácticas dentro del repositorio (como creación de archivos, ramas, resolución de conflictos, etc.).
- Cada pregunta debe estar **etiquetada con un tag**, únicamente en el commit final correspondiente, con el formato: `"Pregunta 1"`, `"Pregunta 2"`, etc.

---

## Pregunta 1 (1 punto)

**Explicar la diferencia entre los siguientes conceptos/comandos en Git y GitHub:**

- `git clone`  
- `fork`  
- `git pull`

### Parte práctica:

- Realizar un **fork** de este repositorio en la cuenta personal de GitHub del estudiante.
- Luego, realizar un **clone** del fork en el equipo local.
- En este README, describir el proceso seguido:
  - ¿Cómo se realizó el fork?
  - ¿Cómo se realizó el clone del fork?
  - ¿Cómo se verificó que se estaba trabajando sobre el fork y no sobre el repositorio original?

**📝 Respuesta:**

**Diferencias:**

- **`git clone`:** Comando de Git que descarga una copia completa de un repositorio remoto (incluyendo historial y ramas) a tu equipo local.
- **`fork`:** Acción en GitHub que crea una copia del repositorio en tu propia cuenta, permitiendo trabajar de forma independiente del original.
- **`git pull`:** Comando de Git que actualiza tu repositorio local trayendo y fusionando los últimos cambios del repositorio remoto.

**Proceso seguido:**

- **Fork:** Ingresé al repositorio original en GitHub y presioné el botón "Fork" para crear una copia en mi cuenta personal.  
  ![Evidencia de fork](img/fork.png)

- **Clone:** En mi cuenta, copié la URL del fork y ejecuté en la terminal:  
  `git clone https://github.com/miusuario/nombre-del-repositorio.git`  
  ![Evidencia de git clone](img/gitclone.png)
  
- **Verificación:** Usé el comando `git remote -v` y comprobé que la URL remota corresponde a mi fork (mi usuario), no al repositorio original.  
  ![Evidencia de git remote -v](img/gitremote-v.png)

---

## Pregunta 2 (1 punto)

**Configurar un archivo `.gitignore` para que ignore:**

- Todos los archivos con extensión `.log`.
- Una carpeta llamada `temp/`.
- Todos los archivos `.md` y `.txt`de la carpeta `doc/`. (Probar agregando un archivo `prueba.md` y un archivo `prueba.txt` dentro de la carpeta y fuera de la carpeta.)

### Requisitos:

1. Realizar un **primer commit** que incluya únicamente el archivo `.gitignore` con las reglas de exclusión definidas.
2. Realizar un **segundo commit** donde se explique en este README la función del archivo `.gitignore` y se muestre evidencia de que los archivos y carpetas indicadas no están siendo rastreadas por Git.

**Importante:**  
- Solo el **segundo commit** debe llevar el **tag `"Pregunta 2"`**.

**📝 Respuesta:**

**Función del archivo `.gitignore`:**

El archivo `.gitignore` sirve para indicarle a Git qué archivos o carpetas no deben ser rastreados ni incluidos en el control de versiones. Esto es útil para evitar subir archivos temporales, de configuración local, o archivos generados automáticamente que no son relevantes para el repositorio.

**Evidencia de exclusión:**

- Se creó un archivo `.gitignore` con las siguientes reglas:
  - Ignorar todos los archivos `.log`.
  - Ignorar la carpeta `temp/`.
  - Ignorar todos los archivos `.md` y `.txt` dentro de la carpeta `doc/`.

  ![Evidencia primer commit .gitignore](img/primercommit,pregunta2.png)

- Se agregaron archivos de prueba:
  - `doc/prueba.md` y `doc/prueba.txt` (estos archivos no son rastreados por Git).
  - `prueba.md` y `prueba.txt` fuera de la carpeta `doc/` (estos sí son rastreados).
  - Archivos `.log` y la carpeta `temp/` tampoco son rastreados.

  ![Agregar archivos no rastreados](img/Agregararchivosnorastreados7.png)

- Evidencia del comando `git status` mostrando que los archivos y carpetas indicados no aparecen como cambios a ser rastreados:

  ![Evidencia de git status](img/gitstatyusp2.png)

---

## Pregunta 3 (2 puntos)

**Utilizar Git Flow para desarrollar una nueva funcionalidad llamada `ingresar-encabezado`.**

### Comandos exactos utilizados

```bash
# Inicializar Git Flow en el repositorio
git flow init -d
```
![Evidencia git flow init](img/gitflowinit.png)

```bash
# Crear y empezar un hotfix llamado ingresar-encabezado
git flow hotfix start ingresar-encabezado
```
![Inicio hotfix](img/edicionencabezado.png)

```bash
# (Editar el README.md para completar los datos personales en el encabezado)

# Agregar y commitear los cambios realizados
git add README.md
git commit -m "Completar encabezado con datos personales"
```
![Commit cambios encabezado](img/agregarycomitearcambios.png)

```bash
# Finalizar el hotfix (esto fusiona los cambios en main y develop, y crea un tag)
git flow hotfix finish ingresar-encabezado
```
![Finalizar hotfix](img/finhotfix.png)

```bash
# Subir los cambios y los tags al repositorio remoto
git push origin main
git push origin develop
git push origin --tags
```
![Subir cambios al remoto](img/subircambiosalremoto.png)

### Descripción del proceso seguido

1. **Inicialización de Git Flow:**  
   Se ejecutó `git flow init` para configurar el flujo de trabajo con las ramas principales `main` y `develop`.  
   ![Evidencia git flow init](img/gitflowinit.png)

2. **Creación del hotfix:**  
   Se creó una rama de tipo hotfix llamada `ingresar-encabezado` con `git flow hotfix start ingresar-encabezado`.  
   ![Inicio hotfix](img/edicionencabezado.png)

3. **Desarrollo en la rama hotfix:**  
   Se completó el encabezado del archivo `README.md` con los datos personales del estudiante y se realizó un commit.  
   ![Commit cambios encabezado](img/agregarycomitearcambios.png)

4. **Finalización del hotfix:**  
   Se ejecutó `git flow hotfix finish ingresar-encabezado`, lo que fusionó los cambios tanto en `main` como en `develop`, eliminó la rama hotfix y creó un tag correspondiente.  
   ![Finalizar hotfix](img/finhotfix.png)

5. **Subida de cambios:**  
   Se subieron las ramas y los tags al repositorio remoto con los comandos `git push`.  
   ![Subir cambios al remoto](img/subircambiosalremoto.png)

### Ventajas de aplicar Git Flow

- **Organización:** Permite separar claramente el desarrollo de nuevas funcionalidades, correcciones urgentes y lanzamientos.
- **Colaboración:** Facilita el trabajo en equipo, ya que cada tipo de tarea tiene su propio flujo y ramas específicas.
- **Control de versiones:** Ayuda a mantener un historial limpio y estructurado, ideal para proyectos de larga duración y equipos grandes.
- **Reducción de errores:** Minimiza los conflictos y errores al tener procesos definidos para cada tipo de cambio.

---

## Pregunta 4 (2 puntos)

**Trabajo con Issues y Pull Requests**

### Parte teórica:

- **¿Qué es un issue en GitHub?**  
  Un **issue** es una herramienta de GitHub que permite reportar tareas, errores, mejoras o preguntas relacionadas con un proyecto. Los issues ayudan a organizar y dar seguimiento al trabajo pendiente o a problemas detectados en el repositorio.

- **¿Qué es un pull request y cuál es su finalidad?**  
  Un **pull request** (PR) es una solicitud para fusionar cambios realizados en una rama (por ejemplo, `develop`) hacia otra rama (por ejemplo, `main`). Su finalidad es revisar, discutir y aprobar los cambios antes de integrarlos al código principal del proyecto.

- **Diferencia y relación entre ambos:**  
  Un **issue** sirve para identificar y discutir tareas o problemas, mientras que un **pull request** se utiliza para proponer la integración de cambios al repositorio. En un entorno colaborativo, los issues pueden dar origen a ramas de trabajo y, una vez resueltos, los cambios se integran mediante un pull request. Además, los pull requests pueden estar vinculados a issues para cerrar automáticamente el issue cuando el PR es fusionado.

### Resumen del procedimiento realizado

1. Se creó un **issue** titulado `"Respuesta a la Pregunta 4"` para documentar la respuesta a esta pregunta.  
   ![Evidencia creación issue](img/creacionIssue.png)

2. Se editó el archivo `README.md` en la rama `develop` para responder la pregunta 4.

3. Se realizó un commit con los cambios y se subió a la rama `develop` del repositorio remoto.  
   ![Commit cambios develop](img/cambioDevelop.png)
   ![Push a develop](img/gitpushorigindevelop.png)

4. Se creó un **pull request** desde la rama `develop` hacia la rama `main` en GitHub.  
   ![Evidencia crear pull request](img/crearPullRequest.png)

5. El pull request fue vinculado al issue creado, de modo que al aprobar y fusionar el PR, el issue se cerró automáticamente.  
   ![Evidencia pull request vinculado](img/Captura\ de\ pantalla\ 2025-10-07\ 164106.png)
   ![Evidencia merge pull request](img/mergePullRequest.png)
  

6. Finalmente, se aprobó y fusionó el pull request.  
   ![Evidencia final pull request](img/CFinalPullRequest.png)


---

## Pregunta 5 (2 puntos)

**Resolver conflictos entre ramas y realizar un Pull Request**

### Requisitos:

- Crear dos ramas llamadas `ramaA` y `ramaB`, ambas a partir de la rama `develop`.
- En `ramaA`, crear un archivo llamado `archivoA.txt` con el contenido:  
  `Contenido A`
- En `ramaB`, crear un archivo con el mismo nombre (`archivoA.txt`), pero con el contenido:  
  `Contenido B`
- Intentar fusionar `ramaB` sobre `ramaA`, lo cual debe generar un conflicto.
- Resolver el conflicto combinando ambos contenidos.
- Realizar el merge de `ramaA` hacia `develop`.
- Crear un **pull request** desde `develop` hacia `main`.
- Una vez completado lo anterior, eliminar las ramas `ramaA` y `ramaB` tanto local como remotamente.

### En este README, se debe incluir:

- El procedimiento completo:
  - Cómo se crearon las ramas.
  - Cómo se generó y resolvió el conflicto.
  - Cómo se realizó el merge hacia `develop`.
  - Cómo se eliminaron las ramas al finalizar.
- El enlace al pull request.
- Una breve explicación de qué es un conflicto en Git y por qué ocurrió en este caso.

**📝 Respuesta:**

### Procedimiento realizado

1. **Creación de ramas:**
   - Se crearon dos ramas llamadas `ramaA` y `ramaB` a partir de la rama `develop`.

2. **Creación y edición de archivos:**
   - En la rama `ramaA`, se creó el archivo `archivoA.txt` con el contenido:  
     `Contenido A`
   - En la rama `ramaB`, se creó el archivo `archivoA.txt` con el contenido:  
     `Contenido B`

3. **Generación y resolución del conflicto:**
   - Al intentar fusionar `ramaB` sobre `ramaA`, Git detectó un conflicto en el archivo `archivoA.txt` porque ambos tenían cambios diferentes en la misma línea.
   - El conflicto se resolvió combinando ambos contenidos en el archivo, quedando así:
     ```
     Contenido A
     Contenido B
     ```

4. **Merge hacia develop:**
   - Se realizó el merge de la rama `ramaA` (ya sin conflictos) hacia la rama `develop`.

5. **Pull request:**
   - Se creó un pull request desde la rama `develop` hacia la rama `main`.

6. **Eliminación de ramas:**
   - Finalmente, se eliminaron las ramas `ramaA` y `ramaB` tanto local como remotamente.

### Explicación de conflicto en Git

Un **conflicto en Git** ocurre cuando dos ramas modifican la misma parte de un archivo de forma diferente y Git no puede decidir automáticamente cuál cambio conservar. En este caso, el conflicto ocurrió porque tanto `ramaA` como `ramaB` crearon un archivo con el mismo nombre pero con contenidos distintos en la misma línea.

### Enlace al pull request



---

## Pregunta 6 (2 puntos)

**Realizar limpieza, explicar versionamiento semántico y enviar cambios al repositorio original**

### Requisitos:

- Trabajar en la rama `develop` del fork del repositorio.
- Eliminar los archivos `archivoA.txt` y `archivoB.txt` creados en preguntas anteriores.
- Realizar un merge desde `develop` hacia `main` en el repositorio local.
- Enviar los cambios de la rama `main` local a la rama `develop` del repositorio remoto (fork). Recuerde incluir todos los tags creados (6 tags).
- Finalmente, crear un **pull request** desde la rama `develop` del fork hacia la rama `main` del repositorio original (del cual se realizó el fork en la Pregunta 1). El titulo del pull request debe ser "NOMBRE APELLIDOS", en la descripción colocar el link de su repositorio de GitHub.

### En este README, se debe incluir:

- Una explicación del proceso realizado paso a paso.
- Una explicación del **versionamiento semántico**, indicando:
  - En qué consiste.
  - Sus tres componentes (MAJOR, MINOR, PATCH).
- El enlace al pull request creado hacia el repositorio original.
- Si hace falta agregar alguna evidencia adicional, agregue un tag adicional que sea `Version Final`.

**📝 Respuesta:**

<!-- Escribe aquí tu respuesta completa a la Pregunta 6 -->
