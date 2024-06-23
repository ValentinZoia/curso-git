![1675016970735.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/1675016970735.png)

![Captura de pantalla 2024-06-22 185207.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-22_185207.png)
# Git y Github

## Qué es Git?

Git es un sistema de control de versiones distribuido, diseñado para gestionar y coordinar el trabajo de desarrollo de software entre varios programadores.

Trabaja de forma local en tu computadora, en el cual hace capturas de las distintas versiones de tu código.

Abrir gitbash y configurar lo siguiente:

```bash
git config --global user.name "Tu nombre" 

git config --global user.email example@gmail.com

git config --global core.editor "code --wait" //visual studio

git config --global core.autocrlf true //salto d linea windows

```

## Comandos Básicos

- ls : listado de carpetas dentro de donde estamos parados.
- cd: entrar a carpeta
- cd .. : salir de la carpeta (ir a la anterior)
- pwd : dirección / ruta completa
- clear: limpiar terminal
- mkdir: crear directorio

## Inicializar proyecto en git

Ubicarnos en carpeta donde queremos tenerlo. Abrir terminal y colocar:

```bash
git init
```

### Git Status, Add y Commit

### 1. `git status`

El comando `git status` se utiliza para mostrar el estado del directorio de trabajo y el área de preparación. Te muestra los cambios que se han hecho en tu repositorio pero que aún no se han confirmado.

```bash
git status
```

Este comando te mostrará:

- Archivos modificados que aún no han sido añadidos al área de preparación.
- Archivos en el área de preparación listos para ser confirmados.
- Archivos que no están siendo rastreados por Git.

### 2. `git add`

El comando `git add` se utiliza para agregar cambios al área de preparación. Puedes agregar archivos específicos o todos los cambios a la vez.

Para agregar un archivo específico:

```bash
git add nombre_del_archivo
```

Para agregar todos los archivos y cambios:

```bash
git add .
```

### 3. `git commit`

El comando `git commit` se utiliza para confirmar los cambios en el área de preparación y guardarlos en el historial del repositorio. Debes proporcionar un mensaje de confirmación que describa los cambios.

```bash
git commit -m "Mensaje de confirmación"
```

Asegúrate de que tu mensaje de confirmación sea claro y descriptivo para que otros desarrolladores (o tú mismo en el futuro) puedan entender qué cambios se hicieron.

### Flujo de Trabajo Básico

1. **Verificar el estado del repositorio:**
    
    ```bash
    git status
    ```
    
2. **Agregar cambios al área de preparación:**
    - Para agregar archivos específicos:
        
        ```bash
        git add nombre_del_archivo
        ```
        
    - Para agregar todos los cambios:
        
        ```bash
        git add .
        ```
        
3. **Confirmar los cambios:**
    
    ```bash
    git commit -m "Descripción clara de los cambios
    ```
    

### Ejemplo Completo

Imagina que has modificado un archivo llamado `index.html` y quieres confirmarlo:

1. Verificar el estado del repositorio:
    
    ```bash
    git status
    ```
    
2. Agregar `index.html` al área de preparación:
    
    ```bash
    git add index.html
    ```
    
3. Confirmar los cambios:
    
    ```bash
    git commit -m "Actualizar el archivo index.html con el nuevo diseño de la página principal"
    ```
    

Este flujo de trabajo es esencial para gestionar tus cambios en Git y mantener un historial claro y organizado de tus modificaciones.

### Sacar archivos del stage

```bash
git rm --cached <file>
```

Con el ejemplo anterior si queremos sacar index.html del stage seria asi:

```bash
git rm --cached index.html
```

y si lo queremos volver a agregar. le hacemos el git add.  

## Git Ignore

El archivo `.gitignore` se utiliza en Git para especificar archivos y directorios que Git debe ignorar. Esto es útil para evitar que archivos no deseados (como archivos temporales, binarios compilados, configuraciones locales, etc.) sean incluidos en el control de versiones.

Ejemplo

Generalmente el archivo .env donde tenemos nuestras variables de entorno, si o si se ignora, porque podemos tener contraseñas, nombres de usuario, etc.

La carpeta node_modules. Si creamos un proyecto que utiliza node, se crea esta carpeta donde están todos los módulos instalados, que la verdad no nos interesa sus seguimiento.

```
.env
node_modules
```

## Git diff

El comando `git diff` en Git se utiliza para mostrar las diferencias entre varias versiones de archivos en tu repositorio. Es una herramienta poderosa para revisar cambios antes de confirmarlos, ver lo que ha cambiado en tu código y comparar diferentes ramas o commits.

### Uso Básico de `git diff`

1. **Ver diferencias no confirmadas:**
    
    Para ver los cambios que has hecho en el directorio de trabajo pero que aún no has agregado al área de preparación:
    
    ```bash
    git diff
    ```
    

El comando `git log` se utiliza para ver el historial de commits en un repositorio Git. Este comando muestra una lista de commits en orden cronológico inverso, comenzando por el commit más reciente.

## Git log

### Uso Básico de `git log`

```bash
git log
```

Cuando ejecutas `git log`, verás información detallada sobre cada commit, incluyendo:

- El hash del commit (una cadena larga y única).
- El autor del commit.
- La fecha y hora del commit.
- El mensaje de confirmación (commit message).

### Opciones Comunes de `git log`

1. **Mostrar un número específico de commits:**
    
    Para limitar el número de commits mostrados:
    
    ```bash
    git log -n <número>
    ```
    
    Por ejemplo, para mostrar los últimos 3 commits:
    
    ```bash
    git log -n 3
    ```
    
    O, más comúnmente:
    
    ```bash
    git log -3
    ```
    
2. **Formato compacto (una línea por commit):**
    
    Para mostrar cada commit en una sola línea:
    
    ```bash
    git log --oneline
    ```
    
3. **Mostrar diferencias de cada commit:**
    
    Para incluir los cambios introducidos por cada commit (un diff patch):
    
    ```bash
    git log -p
    ```
    
4. **Estadísticas de diferencias:**
    
    Para mostrar estadísticas de los cambios en lugar del diff completo:
    
    ```bash
    git log --sta
    ```
    
5. **Filtrar por autor:**
    
    Para mostrar los commits hechos por un autor específico:
    
    ```bash
    git log --author="Nombre del Autor"
    ```
    
6. **Filtrar por palabra clave en el mensaje de confirmación:**
    
    Para buscar commits que contengan una palabra clave en el mensaje de confirmación:
    
    ```bash
    git log --grep="palabra clave"
    
    ```
    
7. **Rango de fechas:**
    
    Para mostrar commits realizados dentro de un rango de fechas específico:
    
    ```bash
    
    git log --since="2022-01-01" --until="2022-12-31"
    
    ```
    
8. **Gráfico de ramas:**
    
    Para ver un gráfico de las ramas junto con los commits:
    
    ```bash
    
    git log --graph --oneline --all
    
    ```
    

### Ejemplos Prácticos

1. **Mostrar los últimos 5 commits en un formato compacto:**
    
    ```bash
    
    git log -5 --oneline
    
    ```
    
2. **Mostrar commits con diferencias para un archivo específico:**
    
    ```bash
    
    git log -p nombre_del_archivo
    
    ```
    
3. **Mostrar commits de un autor específico:**
    
    ```bash
    
    git log --author="John Doe"
    
    ```
    
4. **Mostrar commits con una palabra clave específica en el mensaje:**
    
    ```bash
    
    git log --grep="bugfix"
    
    ```
    
5. **Mostrar commits realizados en los últimos dos semanas:**
    
    ```bash
    
    git log --since="2 weeks ago"
    
    ```
    

### Combinaciones Útiles

Puedes combinar varias opciones para afinar tu búsqueda. Por ejemplo, para mostrar los últimos 5 commits de un autor específico en un formato compacto:

```bash

git log -5 --oneline --author="John Doe"

```

### Navegación Interactiva

`git log` puede producir mucha información, especialmente en proyectos grandes. Para navegar de manera interactiva:

```bash

git log

```

Luego, usa las teclas de flecha para desplazarte, y presiona `q` para salir.

### Alias Útiles

Para facilitar el uso de `git log`, puedes configurar alias en tu archivo de configuración de Git (`.gitconfig`). Por ejemplo:

```

[alias]
    l = log --oneline --graph --decorate --all

```

Ahora, simplemente puedes usar `git l` para ver un log gráfico compacto y decorado de todos los commits.

```bash

git l

```

El comando `git log` es muy flexible y se puede personalizar para adaptarse a tus necesidades de seguimiento y revisión del historial de commits en tu proyecto.

Para salir ponemos `..q` 

## Brench / rama

En Git, una rama (branch) es una línea de desarrollo independiente dentro de un repositorio. Las ramas te permiten trabajar en diferentes características, correcciones de errores, o versiones de tu proyecto de manera aislada. Esto significa que puedes desarrollar y probar nuevas ideas sin afectar la línea principal de desarrollo (generalmente llamada `master` o `main`).

### Conceptos Clave de las Ramas en Git

1. **Crear una Rama**: Cuando creas una nueva rama, Git copia el estado actual del proyecto en esa nueva rama. A partir de ese punto, puedes realizar cambios en la nueva rama sin afectar otras ramas.
2. **Cambiar entre Ramas**: Puedes cambiar fácilmente entre ramas usando el comando `git checkout` o el más reciente `git switch`.
3. **Combinar Ramas (Merge)**: Una vez que hayas terminado de trabajar en una rama y estés listo para integrar los cambios en otra rama, puedes "fusionar" (merge) las ramas.
4. **Eliminar Ramas**: Después de fusionar una rama y si ya no la necesitas, puedes eliminarla para mantener tu repositorio limpio.

### Comandos Básicos de Ramas en Git

Preguntar en qué rama estamos

```

git branch

```

1. **Crear una nueva rama**:
    
    ```
    
    git branch nombre-de-la-rama
    
    ```
    
2. **Cambiar a una rama existente**:
    
    ```
    
    git checkout nombre-de-la-rama
    
    ```
    
    O con el nuevo comando `switch`:
    
    ```
    
    git switch nombre-de-la-rama
    
    ```
    
3. **Crear y cambiar a una nueva rama en un solo paso**:
    
    ```
    
    git checkout -b nombre-de-la-rama
    
    ```
    
    O con el nuevo comando `switch`:
    
    ```
    
    git switch -c nombre-de-la-rama
    
    ```
    
4. **Fusionar una rama en la rama actual**:
    
    Primero, asegúrate de estar en la rama en la que deseas fusionar los cambios. Luego, ejecuta:
    
    por ejemplo: creamos una rama llamada nuevaRama y en ella modificamos cosas e hicimos un commit. para fusionarla con la rama master, volvemos a la master con git checkout master y escribimos el siguiente comando para fusionarlas.
    
    ```
    
    git merge nuevaRama
    
    ```
    
5. **Eliminar una rama**:
    
    ```
    
    git branch -d nombre-de-la-rama
    
    ```
    
    Forzar la eliminación de una rama:
    
    ```
    
    git branch -D nombre-de-la-rama
    
    ```
    

### Ejemplo de Flujo de Trabajo con Ramas

1. **Crear una nueva rama para una nueva característica**:
    
    ```
    
    git checkout -b feature/nueva-caracteristica
    
    ```
    
2. **Realizar cambios y confirmarlos (commits)**:
    
    ```
    
    git add .
    git commit -m "Implementa nueva característica"
    
    ```
    
3. **Cambiar a la rama principal (main o master)**:
    
    ```
    
    git checkout main
    
    ```
    
4. **Fusionar la nueva característica en la rama principal**:
    
    ```
    
    git merge feature/nueva-caracteristica
    
    ```
    
5. **Eliminar la rama de la nueva característica (opcional)**:
    
    ```
    
    git branch -d feature/nueva-caracteristica
    
    ```
    

### Beneficios de Usar Ramas

- **Aislamiento**: Puedes trabajar en nuevas características o correcciones de errores sin afectar la estabilidad del proyecto principal.
- **Colaboración**: Los equipos pueden trabajar en paralelo en diferentes ramas y luego combinar sus cambios.
- **Gestión de versiones**: Facilita la gestión de versiones y lanzamientos, permitiendo mantener ramas específicas para versiones estables, desarrollo, etc.

## Git push, git pull

### Git Push

- Imagina que estás trabajando en un proyecto de programación con otras personas, y todos están utilizando una carpeta compartida para guardar el código del proyecto. Cada vez que haces cambios en tu parte del código, esos cambios se guardan en tu carpeta local.
- Sin embargo, para que todos en el equipo vean tus cambios y puedan trabajar con ellos, necesitas “empujar” esos cambios a la carpeta compartida en línea, que es como el lugar central donde se guarda todo el código del proyecto. Cuando ejecutas el comando “GIT PUSH” en tu pc, le estas diciendo a Git (una herramienta para gestionar versiones de  código) que tome tus cambios y los suba a esa carpeta compartida en línea.
- Entonces, en resumen, “GIT PUSH” es como presionar un botón para compartir tus cambios con el equipo, para que todos puedan ver y trabajar con ellos en el proyecto.

### Git Pull

- Imagina que estás trabajando en un proyecto de programación con otras personas, y todos están utilizando una carpeta compartida en línea para guardar el código del proyecto. Cada vez que alguien más hace cambios en ese código y los guarda en esa carpeta compartida, esos cambios no se reflejan automáticamente en tu copia local de ese código en tu pc.
- Para obtener los últimos cambios que otros hayan hecho en el proyecto y sincronizarlo con tu copia local, utilizas el comando “GIT PULL”. Esto le dice a GIT(la herramienta que gestiona las versiones de código) que vaya a la carpeta compartida en línea, obtenga los cambios mas recientes y los traiga a tu computadora para que puedas trabajar con ellos.

## Enlazar a repositorio remoto

Abrimos nuestro github: 

[GitHub: Let’s build from here](https://github.com/)

Ya logeados, creamos un nuevo repositorio. Damos a New, botón ubicado arriba a la izquierda en verde.

![Captura de pantalla 2024-06-22 185207.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-22_185207.png)

Luego te dirigira a una pagina de configuracion. En ella como primer paso colocamos el nombre del repositorio, por ejemplo proyecto-git. 

Como segundo paso, creamos el repositorio. Clickeamos el botón verde que dice Create Repository

![Captura de pantalla 2024-06-22 185557.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-22_185557.png)

Luego, nos dirigirá a la siguiente página, donde cumpliremos los pasos `1` y copiaremos el link `2` y lo pegaremos en nuestra terminal.

![Captura de pantalla 2024-06-22 191151.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-22_191151.png)

Por último hacemos `git push origin master`  este comando se usa solo como primera vez luego de enlazar a repositorio remoto.

![Captura de pantalla 2024-06-22 191624.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-22_191624.png)

### Error con git pull

Si subimos o modificamos archivos de forma remota. Osea desde la web de github. Para traer los cambios o creaciones a nuestro repositorio local, usamos git pull.

Pero puede surgir un error si es la primera vez que configuras/enlazas el repositorio.

![Captura de pantalla 2024-06-22 192640.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-22_192640.png)

Esto se soluciona con la siguiente linea de codigo:

```
git branch -u origin/master
```

y listo, ya podemos hacer `git pull` y seguir con nuestro trabajo.

Y por último si hay una rama que creaste localmente y cuando enlazaste a repositorio remoto no aparece, lo solucionas con el siguiente código.

```
git push --set-upstream origin <nombre-de-la-rama>
```

## Git tag, git switch

### Git Tag

Nos va a permitir taguear o etiquetar uno de los commits como un commit importante. Por ejemplo se utiliza mucho cuando vamos a sacar una versión a producción o a nivel público, normalmente se taguea porque es una versión fuerte, una versión estable, la cual vamos a poder publicarla y de esa forma nos queda esa etiqueta por si después la modificamos y queremos volver a un punto donde era estable. De todas formas por supuesto después se van haciendo varias etiquetas y a lo largo del tiempo se va viendo el avance de las distintas versiones de nuestro código.

### Tipos de Etiquetas

1. **Etiqueta Ligera**: Esencialmente un puntero a un commit específico.
2. **Etiqueta Anotada**: Almacena metadatos adicionales como el nombre del etiquetador, correo electrónico, fecha y un mensaje de la etiqueta. Este tipo se almacena como un objeto completo en la base de datos de Git.

### Crear Etiquetas

1. **Etiqueta Ligera**
    
    ```bash
    git tag <nombre_etiqueta>
    ```
    
    Ejemplo:
    
    ```bash
    git tag v1.0
    ```
    
2. **Etiqueta Anotada**
    
    ```bash
    git tag -a <nombre_etiqueta> -m "Mensaje de la etiqueta"
    ```
    
    Ejemplo:
    
    ```bash
    git tag -a v1.0 -m "Versión de lanzamiento 1.0
    ```
    

### Listar Etiquetas

Para listar todas las etiquetas en tu repositorio:

```bash
git tag
```

Para obtener información más detallada, incluyendo el mensaje de la etiqueta (para etiquetas anotadas):

```bash
git show <nombre_etiqueta>
```

Ejemplo:

```bash
git show v1.0
```

### Enviar Etiquetas al Repositorio Remoto

Las etiquetas no se envían automáticamente al repositorio remoto. Debes enviarlas explícitamente.

Para enviar una sola etiqueta:

```bash
git push origin <nombre_etiqueta>
```

Ejemplo:

```bash
git push origin v1.0
```

Para enviar todas las etiquetas de una vez:

```bash
git push origin --tags
```

### Cambiar a una Etiqueta

Puedes cambiar a una etiqueta específica, pero esto pone tu repositorio en un estado de "detached HEAD", lo que significa que cualquier commit que hagas no estará en una rama.

```bash
git checkout <nombre_etiqueta>
```

Ejemplo:

```bash
git checkout v1.0
```

### Eliminar Etiquetas

1. **Localmente**
    
    ```bash
    git tag -d <nombre_etiqueta>
    ```
    
    Ejemplo:
    
    ```bash
    git tag -d v1.0
    ```
    
2. **Remotamente**
    
    Primero, elimina la etiqueta local:
    
    ```bash
    git tag -d v1.0
    ```
    
    Luego, elimina la etiqueta del repositorio remoto:
    
    ```bash
    git push origin --delete <nombre_etiqueta
    ```
    
    Ejemplo:
    
    ```bash
    git push origin --delete v1.0
    ```
    

### Resumen de Comandos Comunes

- Crear una etiqueta ligera: `git tag <nombre_etiqueta>`
- Crear una etiqueta anotada: `git tag -a <nombre_etiqueta> -m "Mensaje de la etiqueta"`
- Listar todas las etiquetas: `git tag`
- Mostrar detalles de una etiqueta: `git show <nombre_etiqueta>`
- Enviar una sola etiqueta al remoto: `git push origin <nombre_etiqueta>`
- Enviar todas las etiquetas al remoto: `git push origin --tags`
- Eliminar una etiqueta localmente: `git tag -d <nombre_etiqueta>`
- Eliminar una etiqueta del remoto: `git push origin --delete <nombre_etiqueta>`

### Git switch

El comando `git switch` es una alternativa moderna y más específica a `git checkout` para cambiar entre ramas y crear nuevas ramas en Git. Fue introducido en Git 2.23 para hacer la interfaz de usuario más clara y menos propensa a errores. Aquí te explico cómo usar `git switch` y en qué casos se utiliza.

### Usos de `git switch`

1. **Cambiar a una Rama Existente**
2. **Crear y Cambiar a una Nueva Rama**
3. **Cambiar a una Rama Creando una Nueva si No Existe**

### 1. Cambiar a una Rama Existente

Si quieres cambiar a una rama que ya existe, puedes usar:

```bash
git switch <nombre-de-rama>
```

Ejemplo:

```bash
git switch main
```

### 2. Crear y Cambiar a una Nueva Rama

Si deseas crear una nueva rama y cambiarte a ella inmediatamente, puedes usar:

```bash
git switch -c <nombre-de-nueva-rama>
```

Ejemplo:

```bash
git switch -c nueva-rama
```

Esto es equivalente a:

```bash
git checkout -b nueva-ram
```

### 3. Cambiar a una Rama Creando una Nueva si No Existe

Si quieres cambiar a una rama y crearla si no existe, pero solo si es un cambio de rama directo, no hay una opción directa en `git switch`. Tendrías que primero verificar si la rama existe y luego cambiar o crear y cambiar:

```bash
git switch <nombre-de-rama> || git switch -c <nombre-de-rama>
```

### Otras Opciones Útiles

- **Cambiar a una rama específica y restablecer el directorio de trabajo**:
    
    ```bash
    git switch --discard-changes <nombre-de-rama>
    ```
    
    Esto descartará cualquier cambio no comprometido en el directorio de trabajo.
    
- **Cambiar a un commit específico (Detached HEAD)**:
    
    ```bash
    git switch --detach <commit-hash>
    ```
    
    Esto es similar a `git checkout <commit-hash>`, poniendo el repositorio en un estado de "detached HEAD".
    

### Comparación con `git checkout`

Aunque `git switch` y `git checkout` pueden realizar tareas similares, `git switch` está diseñado para ser más intuitivo y evitar errores comunes asociados con `git checkout`. Aquí hay una comparación:

- `git switch` es solo para cambiar entre ramas y crear nuevas ramas.
- `git checkout` puede cambiar entre ramas, crear nuevas ramas, cambiar a un commit específico, y más.

Ejemplos comparativos:

- Cambiar a una rama:
    - `git checkout main`
    - `git switch main`
- Crear y cambiar a una nueva rama:
    - `git checkout -b nueva-rama`
    - `git switch -c nueva-rama`

### Resumen

El comando `git switch` es una forma más moderna y clara de cambiar entre ramas en Git. Ayuda a evitar la confusión que puede surgir con el comando `git checkout`, al ser más específico en su propósito. Utiliza `git switch` para cambiar de rama de manera más intuitiva y segura, especialmente si estás trabajando con versiones recientes de Git.

## Navegar entre commits y tag

Para ‘navegar’ entre commits o tags, por si queremos ver las diferentes versiones del código.

### Uso del Comando

```bash
git checkout <nombre-de-tag-o-commit>
```

### Propósitos y Contextos

1. **Explorar el Historial del Proyecto**:
    - Puedes usar `git checkout <commit>` para revisar el estado del proyecto en un punto específico del historial. Esto es útil si necesitas ver o revisar cómo era el código en un commit antiguo.
    
    Ejemplo:
    
    ```bash
    git checkout 1a2b3c4d5e
    ```
    
2. **Cambiar a una Etiqueta (Tag)**:
    - Si usas `git checkout <nombre-de-tag>`, puedes cambiar al estado del repositorio en el momento en que se creó esa etiqueta. Esto es útil para revisar el código en una versión específica del proyecto marcada por una etiqueta.
    
    Ejemplo:
    
    ```bash
    git checkout v1.0
    ```
    
3. **Crear una Rama desde un Commit o Tag**:
    - Al cambiar a un commit o tag, el repositorio entra en un estado de "HEAD detached" (cabeza separada), lo que significa que no estás en ninguna rama en particular. Si decides que quieres hacer cambios basados en ese estado, puedes crear una nueva rama a partir de ahí.
    
    Ejemplo:
    
    ```bash
    git checkout -b nueva-rama 1a2b3c4d5
    ```
    

### Importancia del Estado "Detached HEAD"

Cuando usas `git checkout <nombre-de-tag-o-commit>`, Git te coloca en un estado de "detached HEAD". Esto significa que cualquier commit que hagas no se añadirá a ninguna rama actual, sino que creará un nuevo historial separado. Si quieres conservar estos commits, necesitas crear una nueva rama.

### Ejemplos de Uso

1. **Revisar un Commit Específico**:
    - Para ver el estado del repositorio en un commit específico:
    
    ```bash
    git checkout 1a2b3c4d5e
    ```
    
2. **Revisar una Versión Etiquetada**:
    - Para cambiar al estado del repositorio en una versión etiquetada:
    
    ```bash
    git checkout v1.0
    ```
    
3. **Crear una Rama desde una Etiqueta**:
    - Si decides que quieres hacer cambios a partir de una versión etiquetada, primero cambias a esa etiqueta y luego creas una rama:
    
    ```bash
    git checkout v1.0
    git checkout -b nueva-rama
    ```
    

### Resumen

El comando `git checkout <nombre-de-tag-o-commit>` es una herramienta poderosa para navegar y gestionar el historial de tu repositorio Git. Te permite cambiar el estado de tu repositorio a cualquier punto en el tiempo especificado por un commit o una etiqueta. Es especialmente útil para revisar versiones específicas del proyecto, hacer comparaciones, o iniciar nuevas ramas a partir de estados anteriores del proyecto.

## Git stash y Git stash pop

`git stash` y `git stash pop` son comandos útiles para manejar cambios en tu área de trabajo en Git cuando necesitas cambiar de contexto rápidamente, pero no quieres perder tu trabajo actual. Aquí te explico cómo funcionan estos comandos y en qué casos se utilizan:

### `git stash`

El comando `git stash` guarda tus cambios locales (en el directorio de trabajo y el área de preparación) en un stash, y luego restaura el estado de tu directorio de trabajo a la última confirmación (commit). Esto te permite cambiar de rama, realizar otra tarea o actualizar tu repositorio sin perder tus cambios no confirmados.

```bash
git stash
```

### Ejemplo:

Supongamos que estás trabajando en una característica en la rama `feature-branch` y tienes algunos cambios no confirmados. De repente, necesitas cambiar a la rama `main` para revisar un bug urgente. En lugar de confirmar tus cambios a medio terminar, puedes stashearlos:

```bash
# Guarda los cambios no confirmados en un stash
git stash
# Cambia a la rama main
git checkout main
# Haz lo que necesites en la rama main, por ejemplo, revisar un bug
```

### `git stash pop`

El comando `git stash pop` aplica los cambios más recientes del stash a tu directorio de trabajo y elimina esa entrada del stash. Es como si trajeras de vuelta tus cambios no confirmados.

```bash
git stash pop
```

### Ejemplo:

Después de resolver el bug en la rama `main`, decides volver a tu trabajo en la rama `feature-branch`. Primero, cambias de vuelta a `feature-branch`, y luego aplicas los cambios que stasheaste:

```bash
# Cambia de vuelta a feature-branch
git checkout feature-branch
# Aplica los cambios stasheados
git stash pop
```

## Eliminar Ramas (Branches)

Primeramente asegurarnos de estar parados (HEAD) en la rama master.

### Forma Local

Para eliminar la rama de **forma local** escribimos lo siguiente.

```
git branch -d <nombre-rama-a-eliminar>
```

Esto es un paso para eliminarlo por completo, ya que de forma remoto todavía existe esa rama y la podemos traer con un pull.

### Forma Remota

Para eliminar la rama de **forma remota** escribimos lo siguiente.

```
git push origin--delete <nombre-rama-a-eliminar>
```

Este comando elimina la rama de forma local y remota.

## Git Fetch

El comando `git fetch` en Git se utiliza para descargar commits, archivos y referencias desde un repositorio remoto a tu repositorio local. A diferencia de `git pull`, que combina la operación de `fetch` con una operación de `merge` o `rebase`, `git fetch` simplemente actualiza tu copia local del repositorio remoto sin modificar tus ramas de trabajo.

Aquí están los detalles de lo que hace `git fetch`:

1. **Descarga Commits**: Obtiene los commits nuevos de las ramas del repositorio remoto que aún no existen en tu repositorio local.
2. **Actualiza las Referencias Remotas**: Actualiza las referencias de las ramas remotas en tu repositorio local (estas referencias suelen estar en la forma `origin/branchname`).
3. **No Modifica tu Trabajo Actual**: No cambia tu rama actual ni mezcla los cambios descargados con tus archivos de trabajo. Esto te permite revisar los cambios antes de integrarlos.

Por ejemplo, si tienes un repositorio remoto llamado `origin` y ejecutas `git fetch origin`, Git descargará todos los commits, tags y ramas nuevos desde `origin` y actualizará las referencias remotas correspondientes en tu repositorio local. Sin embargo, tus ramas locales y tu directorio de trabajo permanecerán sin cambios hasta que decidas combinar o integrar esos cambios mediante comandos adicionales como `git merge` o `git rebase`.

Este flujo de trabajo es útil porque te permite ver lo que ha cambiado en el repositorio remoto sin afectar tu trabajo actual, y te da la oportunidad de decidir cómo y cuándo integrar esos cambios.

Con el siguiente comando podemos ver todos los commits que se hicieron de forma remota.

```
git fetch
git log --oneline --all
```

Si queremos traer los archivos hacemos `git pull`

## Git Reset

`git reset`  saca del stage los archivos. Supongamos que agregamos al stage un archivo con `git add`  y queremos sacarlos del stage. Solo basta con hacer un `git reset`

Ahora si nosotros queremos sacarlo del stage y volver al commit anterior usamos `git reset —hard` esto es por si no estamos seguros y creemos que hay un error. Volvemos a la versión anterior. Dato: volvemos a la versión anterior de todos los archivos en el stage.

Si queremos hacerlo con un archivo en especial usamos

```
git checkout <nombre-del-archivo>
```

**Si queremos deshacer un commit y descartar todos los cambios en el area de preparacion(stage), mucho cuidado con eso, basta con escribir lo siguiente.**

```
git reset --hard <commit>
```

Haciendo eso eliminas todos los commits posteriores a ese y te ubicas(HEAD) en el commit que marcaste.

**Deshacer el último commit pero mantener los cambios en el área de preparación**:

```bash
git reset --soft <commit>
```

**Deshacer el último commit y quitar los cambios del área de preparación, pero mantenerlos en los archivos del directorio de trabajo**:

```bash
git reset --mixed <commit>
```

## Git Clone

El comando `git clone` se utiliza para crear una copia local de un repositorio remoto. Es una de las primeras operaciones que se realizan al comenzar a trabajar con un repositorio existente, ya que te permite obtener una copia completa de todo el historial del proyecto, incluidas todas las ramas, commits y archivos. Aquí te explico cómo funciona y algunas de sus opciones más comunes.

### Uso Básico

La forma más sencilla de usar `git clone` es:

```bash
git clone <repositorio_remoto>
```

Por ejemplo:

```bash
git clone https://github.com/usuario/nombre-del-repositorio.git
```

Esto hará lo siguiente:

1. **Descargar el Repositorio**: Obtiene todos los archivos y el historial completo del repositorio remoto.
2. **Crear una Carpeta**: Crea una nueva carpeta en tu directorio actual con el nombre del repositorio (a menos que especifiques otro nombre).
3. **Configurar el Repositorio Local**: Configura el repositorio local para que el repositorio remoto se llame `origin`.
4. **Crear y Moverse a la Rama Principal**: Crea la rama principal (a menudo `main` o `master`) y se mueve a ella.

Ejemplo:

Queremos clonar un repositorio remoto. Nos dirigimos hacia ese repositorio en github y clickeamos el botón verde que dice <> Code

Por último copiamos el link.

![Captura de pantalla 2024-06-23 152307.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/c7c05045-82d5-4f3c-aad3-509546e10ac9.png)

En nuestra terminal situados en la carpeta/directorio donde queremos clonar el repositorio escribimos:

```
git clone <link-copiado>
```

## Git merge

Este comando sirve para poder mezclar las ramas (mergear).

El comando `git merge` se utiliza en Git para combinar los cambios de diferentes ramas en una sola rama. Es una de las operaciones clave para integrar el trabajo realizado en diferentes ramas de un proyecto. Aquí hay una explicación detallada sobre cómo funciona y cómo se utiliza `git merge`.

### Uso Básico

La forma básica de usar `git merge` es la siguiente:

```bash
git merge <nombre_de_la_ram
```

Este comando combina la rama especificada (`<nombre_de_la_rama>`) con la rama actual en la que te encuentras.

### Pasos de `git merge`

1. **Cambio a la Rama de Destino**:
Primero, asegúrate de estar en la rama en la que deseas combinar los cambios. Por ejemplo, si quieres combinar cambios en la rama `main`:
    
    ```bash
    git checkout mai
    ```
    
2. **Combinar la Rama**:
Luego, ejecuta el comando de merge para combinar los cambios de otra rama en la rama actual. Por ejemplo, para combinar la rama `feature-branch` en `main`:
    
    ```bash
    git merge feature-branch
    ```
    

### Tipos de Merge

1. **Merge Fast-Forward**:
Si la rama actual no tiene commits nuevos desde que se creó la rama que se está combinando, Git simplemente avanzará el puntero de la rama actual. Esto se llama "fast-forward merge".
    
    ```bash
    git merge feature-branc
    ```
    
    En este caso, si no ha habido cambios en `main` desde que se creó `feature-branch`, Git moverá el puntero de `main` hacia adelante hasta el mismo commit que `feature-branch`.
    
2. **Merge No Fast-Forward (creando un nuevo commit de merge)**:
Si hay commits nuevos en la rama actual que no están en la rama que se está combinando, Git realizará un "merge no fast-forward" y creará un nuevo commit de merge.
    
    ```bash
    git merge --no-ff feature-branch
    ```
    
    Esto es útil para preservar el historial de la rama y para que quede claro que una combinación (merge) ocurrió.
    

### Conflictos

Si mergeamos dos ramas que solucionan un mismo problema en una misma linea de codigo, obvio no podemos quedarnos con las dos, debemos elegir una, por eso se crea un conflicto. Se soluciona facil, solo comparas las dos ramas y elegis la que mas te guste y los subis al stage y haces un commit. Todo esto situados en la rama master. o donde queramos mergear las ramas.

## Fork & Pull Requests

### Fork

Fork es una herramienta la cual podemos hacer un clonado de un repositorio el cual no es nuestro, poder modificarlo y pedirle al autor que haga los cambios que nosotros estamos recomendando.Esta funcionalidad es fundamental en GitHub y se utiliza principalmente para contribuir a proyectos de código abierto, realizar cambios experimentales sin afectar el repositorio original, o incluso para usar el código como base para un nuevo proyecto.

### ¿Cómo se realiza un Fork en GitHub?

Realizar un fork en GitHub es bastante sencillo:

1. **Accede al Repositorio Original**: Ve al repositorio que deseas forkear en la interfaz de GitHub.
2. **Encuentra el Botón de Fork**: En la esquina superior derecha del repositorio, verás un botón que dice "Fork". Al hacer clic en este botón, GitHub iniciará el proceso de crear una copia del repositorio en tu cuenta.
3. **Espera a que se Complete**: GitHub copiará el repositorio original en tu cuenta. Una vez completado, serás redirigido automáticamente a la página de tu copia del repositorio en tu cuenta de GitHub.

![Captura de pantalla 2024-06-23 165216.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-23_165216.png)

### Pull Requests

Después de realizar un fork y realizar cambios en tu copia del repositorio, puedes colaborar con el proyecto original enviando un pull request. Un pull request es una solicitud para que el propietario del repositorio original considere y, potencialmente, incorpore tus cambios en su proyecto principal.

![Captura de pantalla 2024-06-23 165822.png](Git%20y%20Github%207d52d252b5454b4ca41664f2cf38963c/Captura_de_pantalla_2024-06-23_165822.png)