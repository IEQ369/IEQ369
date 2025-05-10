<h1>Clase 1 - Introducción a Git</h1>

<h2>¿Qué es un control de verificaciones?</h2>
<p>
  Un control de verificaciones es un sistema que registra cada cambio que realiza en el código fuente de un proyecto.
  Esto te permite tener un historial de todos los cambios producidos en sus ficheros, saber quién lo hizo y cuándo.
</p>

<h2>¿Por qué es importante un control de versiones?</h2>
<ul>
  <li>Rendimiento, solo se guarda lo necesario</li>
  <li>Seguridad, conserva toda acción</li>
  <li>Flexibilidad, no es necesario un desarrollo lineal</li>
</ul>

<h1>¿Qué es Git?</h1>
<p>
  Git al ser un sistema distribuido, aloja una copia completa del repositorio en cada máquina local que está trabajando en el código.
  Además, puedes tener uno o varios repositorios remotos para sincronizarlos.
</p>

<table>
  <tr>
    <td align="center">
      <img src="https://i.postimg.cc/vZDjL204/a2c1165235c53e8695b8bde7d9ae8366.jpg" width="600">
    </td>
    <td align="center">
      <img src="https://github.com/user-attachments/assets/bd41f269-dab2-4da3-aa4d-79895b4344e0" width="300">
    </td>
  </tr>
</table>

<table>
  <tr>
    <td width="55%">
      <h2>¿Qué es un Repositorio?</h2>
      <p>
        Un pilar de Git son los repositorios.<br>
        Un repositorio es una carpeta en la que se almacenan las diferentes versiones de los ficheros de un proyecto y el histórico de los cambios que se han realizado en ellos.<br>
        Los repositorios pueden ser locales.
      </p>
    </td>
    <td>
      <img src="https://i.postimg.cc/VN42qStF/organization-1.png" width="300">
    </td>
  </tr>
</table>

<h2>Iniciar un proyecto en Git</h2>
<p>
  Para crear un repositorio Local se puede usar el comando <code>git init</code> e indicar el nombre del proyecto. Creara una carpeta configurada y vacía con el nombre que le has indicado.
</p>
<ul>
  <li><code>git init nuevo-proyecto</code></li>
  <li><code>cd nuevo-proyecto</code></li>
</ul>
<p>
  Para repositorios ya existentes, es necesario usar el comando <code>git init</code> dentro de la raíz del directorio del proyecto
</p>
<ul>
  <li><code>cd {directorio del proyecto}</code></li>
  <li><code>git init</code></li>
</ul>

<!------------------------------------------------------------------->

<h1>Clase 2 - States y commits</h1>

<h2>Los 3 estados de Git</h2>

<a href="https://postimg.cc/4KKTMcMj">
  <img src="https://i.postimg.cc/BvpQjcCZ/Captura-de-pantalla-2025-05-06-203756.png" alt="Captura de pantalla"width="50%">
</a>

<h3>Modified</h3>

<p>El archivo ha sido creado, eliminado o contiene cambios que no han sido marcados como confirmados.</p>

<ul>
  <li><code>git status</code>: Para ver el estado de los archivos en el repositorio.</li>
</ul>

<h3>Staged</h3>

<p>El archivo ha sido marcado como preparado para ser confirmado en el repositorio local.</p>

<ul>
  <li><code>git add &lt;archivo&gt;</code>: Para pasar un archivo al área de staging.</li>
</ul>

<h3>Commited</h3>

<p>El archivo se encuentra grabado en el repositorio local. Esta acción recibe el nombre de <em>commit</em>.</p>

<ul>
  <li><code>git commit -m "mensaje"</code>: Para realizar un commit con un mensaje descriptivo.</li>
</ul>

<p>Un commit en Git es como guardar una partida en un videojuego, permitiendo restaurar cambios anteriores. Es fundamental para registrar cambios en un repositorio y se realiza con <code>git commit</code>. El mensaje de un commit es crucial para documentar los cambios realizados y se puede realizar a través de <code>git commit</code> en Git.</p>

<ul>
  <li><code>git restore --staged &lt;archivo&gt;</code>: Se usa para quitar los cambios que has agregado al área de preparación, pero manteniendo esos cambios en tu directorio de trabajo.</li>
</ul>

<h2>¿Qué es un commit?</h2>

<p>Es como guardar partida en un videojuego, tienes tu punto de restauración si te equivocas.</p>

<table>
  <tr>
    <td align="center">
      <a href="https://postimg.cc/Wtt0TdNN">
        <img src="https://i.postimg.cc/mZyj39KH/unnamed.png" alt="Imagen 1" width="900%">
      </a>
    </td>
    <td align="center">
      <a href="https://postimg.cc/RWXj9xDk">
        <img src="https://i.postimg.cc/q7T0skXv/Captura-de-pantalla-2025-05-06-210748.png" alt="Meme Lobo Git" width="60%">
      </a>
    </td>
  </tr>
</table>


<h3>¿Cómo hago un commit?</h3>

<p>Para guardar los cambios en el área de staging, puedes hacer un commit con el siguiente comando:</p>

<ul>
  <li><code>git commit</code></li>
</ul>

<p>Creará un nuevo commit en tu repositorio y añadirá una referencia al commit en la rama en la que estas trabajando. Para añadir directamente un mensaje sin abrir el editor, se usa el parámetro <code>-m</code> o <code>--message:</code></p>

<ul>
  <li><code>git commit -m "mensaje"</code></li>
</ul>

<p>El mensaje específico se usará como título del commit para describir los cambios realizados.</p>

<h3>Hacer commits con múltiples líneas de mensajes</h3>

<ul>
  <li><code>git commit -m "mensaje" -m "mas mensaje"</code></li>
</ul>

<p>El primer <code>-m "mensaje"</code> se usa para proporcionar el mensaje principal del commit. El segundo <code>-m "mas mensaje"</code> se usa para proporcionar un mensaje adicional, que puede ser una explicación más detallada del cambio realizado.</p>

<h3>git commit —ammend</h3>

<p>Se usa para modificar el commit más reciente en tu historial de Git, para corregir el mensaje del commit o agregar cambios olvidados al último commit sin crear uno nuevo.</p>

<ul>
  <li><code>git commit --ammend -m "nuevo mensaje"</code></li>
</ul>

<h2>¿Qué es el HEAD?</h2>

<p>"HEAD" en Git es simplemente un puntero que apunta al commit actual en el que te encuentras. Es como tu posición actual en la historia de tu proyecto. "HEAD" es un punto de referencia que indica dónde te encuentras en la historia de tu proyecto en cualquier momento dado.</p>
<table>
  <tr>
    <td>
        <a href='https://postimg.cc/94HF6xW9' target='_blank'>
          <img src='https://i.postimg.cc/XvpGyhms/El-texto-del-p-rrafo.png' border='0' width="500" alt='El-texto-del-p-rrafo'/></a>
      </a>
    </td>
    <td>
      <img src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" alt="Bongo Cat" width="300">
    </td>
  </tr>
</table>
<h2>Ramas, merge y conflictos</h2>

<h2>¿Qué es una rama?</h2>

<p>
Una rama en Git es una línea independiente de desarrollo. Te permite trabajar en diferentes versiones de tu proyecto simultáneamente, sin interferir con el trabajo en otras ramas. Es como trabajar en diferentes tareas de tu proyecto al mismo tiempo, manteniendo cada tarea separada hasta que estén listas para combinarse.
</p>

<h3>¿Para qué sirven las ramas?</h3>

<p>Permiten realizar un desarrollo no lineal y colaborativo.</p>

<a href="https://postimg.cc/87WyZNd3"><img src="https://i.postimg.cc/bwVKNvZz/R.png" alt="R" width="600"/></a>

<h2>Creando nuestra primera rama</h2>

<p>
El comando <code>git branch</code> nos permite crear, listar, eliminar y renombrar ramas. Para movernos a ella, tendremos que usar el comando <code>git switch</code>.
</p>

<pre><code class="language-bash">
# Creamos la rama
git branch mi-primera-rama

# Cambiamos a la rama mi-primera-rama
git switch mi-primera-rama
</code></pre>

<p>Es posible hacer los dos pasos en uno usando el comando:</p>

<ul>
  <li><code>git switch -c mi-primera-rama</code> Esto creará la rama y te llevará a ella con un solo comando.</li>
  <li><code>git checkout -b mi-primera-rama</code> Esto también creará la rama y te llevará a ella con un solo comando.</li>
</ul>

<!--------------------------------------------------------------------------------------->

<h1>Clase 3 - Fusionar ramas</h1>

<p>
Las bifurcaciones de código que hemos creado en forma de ramas tendrán dos destinos: acabar en el olvido para no terminar en ningún lado o ser fusionada en otra rama.
</p>

<p>
Cuando hablamos de fusión nos referimos a que los cambios que hemos realizado en la rama se integran en otra rama, de forma que el código que habíamos generado en la nueva rama se asimila en otra.
</p>

<h3>Fusinando ramas</h3>

<p>
Empleamos el comando <code>git merge</code> para incorporar los cambios de una rama a la rama en la que nos encontramos en ese momento.
</p>

<table>
  <tr>
    <td align="center">
      <a href='https://postimg.cc/jCT4bB0V'><img src="https://i.postimg.cc/c1g9QNFJ/R.jpg" alt="R" width="500"></a>
    </td>
    <td align="center">
      <img src="https://i.postimg.cc/T3mkft8J/Captura-de-pantalla-2025-05-09-133545.png" width="250">
    </td>
  </tr>
</table>


<pre><code class="language-bash">
# Abrir el editor antes de hacer el commit
git merge --edit

# Evitar commit automáticamente
git merge --no-commit
</code></pre>

<p>
Al ejecutar el comando <code>git merge</code>, se creará un nuevo commit que incluye todos los cambios de la rama origen a la rama en la que nos encontramos ahora.
</p>

<h2>Eliminar ramas ¿por qué?</h2>

<p>
Porque es una buena práctica, además que las ramas tienen un propósito único y corto de periodo.
</p>

<p>
Después de fusionar una rama en otra, es posible querer eliminarla para no dejarla suelta. Para ello puedes usar el comando <code>git branch</code> con el parámetro <code>--delete</code> o, de forma corta, <code>-d</code>.
</p>

<pre><code class="language-bash">
# Borramos la rama llamada "mi-primera-rama"
git branch --delete mi-primera-rama
</code></pre>

<p>
Si hay el caso de querer borrar una rama que no ha sido fusionada previamente, se debe usar el parámetro <code>-D</code>. Este parámetro le indica a Git que borrará la rama sin importar si ha sido fusionada o no.
</p>

<pre><code class="language-bash">
# Borramos la rama llamada "mi-primera-rama"
git branch -D mi-primera-rama
</code></pre>

<h2>Conflictos en Git</h2>

<table>
  <tr>
    <td><img src="https://github.com/user-attachments/assets/7b60c774-eb36-4c07-af5c-7f4f4f323731" alt="Imagen 1" width="250"></td>
    <td><img src="https://github.com/user-attachments/assets/25c848e4-92fa-4f79-b830-a994a50ecfe5" alt="Imagen 2" width="250"></td>
  </tr>
</table>

<p>
¿Qué pasa si al querer fusionar dos ramas, la de destino ha realizado cambios en las mismas líneas de un fichero que los que queremos fusionar?
</p>

<p>Generan conflictos.</p>

<h3>Resolviendo conflictos</h3>

<p>
Al resolver, deberemos decidir entre:
</p>

<ul>
  <li>Nos quedamos con los cambios de la <em>rama main</em>.</li>
  <li>Nos quedamos con los cambios que vienen de la <em>rama changes</em>.</li>
  <li>Modificamos los cambios para hacer una fusión personalizada.</li>
</ul>

<a href="https://postimages.org/"><img src="https://i.postimg.cc/c1Psm0Zk/9a12c881-9c44-4a3d-8ee2-a55cd341d73b.webp" alt="9a12c881-9c44-4a3d-8ee2-a55cd341d73b" width="450"/></a>

<h3>Comandos</h3>

<img src="https://github.com/user-attachments/assets/4650937e-42b8-4ea0-bda9-bdd3ff48d591" width="150">

<p>comandos mencionados en la clase 2 y 3:</p>

<ul>
  <li><code>git branch</code>: Permite crear, listar, eliminar y renombrar ramas.
    <ul>
      <li><code>git branch &lt;nombre de rama&gt;</code></li>
      <li><code>git branch -a</code></li>
      <li><code>git branch -d &lt;nombre de rama&gt;</code></li>
    </ul>
  </li>
  <li><code>git switch</code>: Se utiliza para cambiar de rama.
    <ul>
      <li><code>git switch &lt;nombre de rama&gt;</code></li>
    </ul>
  </li>
  <li><code>git checkout</code>: También se utiliza para cambiar de rama.
    <ul>
      <li><code>git checkout &lt;nombre de rama&gt;</code></li>
    </ul>
  </li>
  <li><code>git merge</code>: Para incorporar los cambios de una rama a la rama en la que nos encontramos.
    <ul>
      <li><code>git merge &lt;nombre de rama&gt;</code></li>
      <li><code>git merge &lt;nombre de rama&gt; --no-f</code></li>
    </ul>
  </li>
  <li><code>git push</code>: Para enviar los cambios confirmados a un repositorio remoto.</li>
  <li><code>git log</code>: Para ver el historial de confirmaciones.
    <ul>
      <li><code>git log --oneline</code>: Para ver el historial de forma resumida.</li>
      <li><code>git log --graph</code>: Para visualizar el historial en forma de grafo.</li>
      <li><code>git log --graph --oneline</code>: Para visualizar el grafo en una línea.</li>
    </ul>
  </li>
</ul>

<!---------------------------------------------------------------------------------->

# Clase 4 - Git y Github

<a href="https://postimg.cc/67tWFLQn" target="_blank"><img src="https://i.postimg.cc/HL7rc6DZ/git-vs-github-1024x512.png" width="80%" alt="git-vs-github-1024x512" /></a>

## Enlazar un repositorio local con un repositorio remoto

como alias podemos usar cualquier nombre, por defecto es **origin** para indicar que el repositorio remoto que estamos sincronizando es el principal.

Github utiliza las direcciones SSH por defecto. Por ello debemos utilizar estas, para añadir un repositorio local, se ejecuta el siguiente comando:

`git Remote add origin <URL>`

### Generar Key SSH

- Listamos las llaves SSH que ya tenemos
    - `ls -al ~/.ssh`
- Crear key SSH
    - ssh-keygen -t rsa -b 4096 -C “tu.email@gmail.com”
    - press enter
    - passphrase
- Poner en marcha la key SSH
    - `eval "$(ssh-agent -s)"`
- Añadir key SSH
    - `ssh-add ~/.ssh/id_rsa`
- Copia en portapapeles
    - `clip < ~/.ssh/id_rsa.pub`
- Pegar en la sección “key”
    - **https://github.com/settings/ssh/new**

## Como forzar un push

El comando **`git push -f`** (o **`git push --force`**) se utiliza para forzar el empuje de tus cambios locales hacia un repositorio remoto, incluso si esto resulta en la pérdida de commits o la reescritura del historial de la rama remota.

- **`git push -f origin main`**

## Clonando repositorio

Para clonar un repositorio remoto necesitamos saber su dirección, que puede ser una dirección HTTPS o SSH.

<p align="center"><a href="https://postimages.org/"><img src="https://i.postimg.cc/MKSRnBTq/Captura-de-pantalla-2024-05-11-194341.png" alt="Captura de pantalla 2024-05-11 19:43:41" width="600"/></a></p>

Para clonar un repositorio remoto con la dirección SSH

`git clone git@github.com:midudev/libro-javascript.git` 

Para clonar un repositorio remoto con la dirección HTTPS

`git clone https://github.com/midudev/libro-javascript.git` 

## Escribiendo en el repositorio remoto

Para enviar *commits* al repositorio remoto *origin* y la rama *main,* deberíamos ejecutar lo siguiente:

`git push origin oigin main` 

subirá los cambios del repositorio local al repositorio remoto con alias origin a la rama main

## Creando una rama remota

```bash
#Creando una rama en el repositorio local
git switch -c website

#Enviar la rama a nuestro repositorio remoto para ello usamos git push:
#git push <alias-repositorio> <rama>
git push origin website
```

Ahora podemos empezara crear commits en nuestro repositorio local y enviarlos al repositorio remoto de la rama que hemos creado

## Eliminar ramas de mi repositorio local

El comando **`git remote prune origin`** se utiliza para eliminar referencias locales a ramas remotas que ya no existen en el repositorio remoto **`origin`**.

```bash
#ejecutamos el comando
git remote prune origin
```
# Push, Pull & Pull request

<a href='https://postimg.cc/HJFFMT7z' target='_blank'><img src='https://i.postimg.cc/fLbs6LzG/Pull-Request.webp' border='0' alt='Pull-Request' width="70%"/></a>

## ¿Cuál es la diferencia entre git push y git pull?

### git push

Nos sirve para **empujar** cualquier cambio o modificación del repositorio local al repositorio remoto

- **`git push`**: Este comando se utiliza para subir los cambios locales a un repositorio remoto.
    - **`git push --all`**
- **`git push --force`** se utiliza para forzar el empuje de tus cambios locales hacia el repositorio remoto, incluso si esto resulta en la pérdida de commits o en la reescritura del historial de la rama remota.
    - **`git push -f`**
- **`git push --set-upstream <remoto> <rama>`**. Este comando te permite establecer la relación de seguimiento entre una rama local y una rama remota.
- **`git push --delete <remoto> <rama>`** Se utiliza para eliminar una rama remota en un repositorio Git.
    - **`git push -d origin <rama>`**
- **`git push -u origin <rama>`** se utiliza para enviar tus cambios locales a una rama específica en el repositorio remoto llamado "origin" y al mismo tiempo establecer esa rama remota como el upstream (seguimiento) de la rama local actual.
- **`git push origin <remoto> <rama_local>:<rama_remota>`**: Se utiliza para subir los cambios de una rama específica al repositorio remoto.

### git pull

Nos sirve para **jalar** o **descargar** los cambios o modificaciones del repositorio remoto al repositorio local.

- **`git pull`**: Se utiliza para traer los cambios del repositorio remoto al repositorio local.
- **`git pull origin <remoto> <rama>`**: Trae los cambios de una rama específica del repositorio remoto a la rama local.
- **`git pull --all`**  Se utiliza para recuperar todas las ramas remotas y fusionarlas en las ramas locales correspondientes. Esto es útil cuando se quiere asegurar que se tienen todas las actualizaciones de todas las ramas remotas en el repositorio local.
- **`git pull --set-upstream origin <rama>`** Realiza dos acciones:
    1. Establece la rama remota **`origin/<rama>`** como el "upstream" de la rama local actual.
    2. Realiza un pull para traer los cambios de la rama remota especificada (**`origin/<rama>`**) y fusionarlos automáticamente con la rama local actual.
- **`git pull origin <rama1> <rama2> <ramaN>`** Realiza un pull de múltiples ramas desde el repositorio remoto llamado "origin" y las fusiona automáticamente con las ramas locales correspondientes.

## ¿Qué es una Pull Request?

Una Pull Request o **PR**, es una petición de cambios que se envía al repositorio.

### ¿Cómo se hace una **PR**?

Tenemos que subir nuestra rama con **`git push`** y hay dos maneras diferentes:

1. La rama la subiste recientemente y aparece la opción en GitHub
> Code
2. Irnos al apartado Pull Request

## Hacer una buena PR

1. **Enfoca tu código en una sola cosa**, es mucho mas fácil revisar y aceptar una Pull Request  que hace una sola cosa a revisar una Pull Request que aprovecha a hacer muchas cosas.
2. **Explica tu Pull Request**, y su una imagen vale mas que mil palabras. ¿Qué puede valer un GIF o un video mostrando la funcionalidad?

## Revisar una PR

1. Proporciona siempre feedback positivo
2. concreción y claridad
3. **Entiende el contexto**, es posible que a veces tengamos que poner paños calientes o parches a nuestro código y que, pese a no ser el más bonito, sí que cumpla su cometido.

### Comandos

<img src="https://i.imgur.com/8wILbyg.gif" alt="Roblox cayendo lentamente" style="width:40%;">

Se mencionaron varios comandos de Git en la clase 4:

1. `git remote add origin <URL>`: Para enlazar un repositorio remoto con un repositorio local.
2. `git push origin <nombre_rama>`: Para sincronizar los cambios del repositorio local con el repositorio remoto.
3. `git branch -d <nombre_rama>`: Para eliminar una rama local.
    1. `git branch -a`: Extiende la salida para incluir todas las ramas, tanto locales como remotas. Esto incluye las ramas locales y todas las ramas remotas que tu repositorio local conoce, aunque estas últimas no estén en tu sistema local.
4. `git fetch`: Para actualizar la información entre el repositorio remoto y el repositorio local.
5. `git switch <nombre_rama>`: Para cambiar a una rama específica.
6. `git tag <nombre_tag>`: Para etiquetar ciertos commits importantes.
7. `git remote remove <nombre_alias>`: Para eliminar un repositorio remoto conectado.
8. **`git remote prune origin`** Se utiliza para eliminar referencias locales a ramas remotas que ya no existen en el repositorio remoto.
9. `git clone <URL_Repositorio>`: Para clonar un repositorio remoto
10. **`git remote -v`**: Se utiliza para mostrar las URL de los repositorios remotos configurados en tu repositorio local.

<!---------------------------------------------------------------------------------------------------------->

# Clase 5 - GitFlow

## Que es GitFlow?

Es el flujode trabajo mas antiguo, utiliza las ramas:
1.- main (o master): contener el codigo de produccion
2.- develop: Código de preproducción que todavía tienen que ser probadas y validadas

<a href='https://postimg.cc/68HsD45q' target='_blank'><img src='https://i.postimg.cc/MGwWf1C7/5e7444cb6b-1458190973507-jpg.png' border='0' alt='5e7444cb6b-1458190973507-jpg' width="50%"/></a>

# Git Flow

1. Feature: caracteristicas nuevas para el proyecto
2. Release: Cambios de ultimo momento
3. Hotfix: Parches o arreglar bugs pequeños

[github.com](https://github.com/OpherV/gitflow4idea/branches/all)

Rama *main* y cualquier otra rama que quiera ser integrada por medio de una Pull Request

<img src="https://i.postimg.cc/0ybtG3sx/Captura-de-pantalla-2024-05-07-212235.png" alt="Captura de pantalla 2024-05-07 212235" style="width:50%;">

## Trunk Based Development

Solo la *rama main* y ramas auxiliares efímeras que quiera ser integrada por medio de una Pull Request.
Es util si contamos con un buen Sistema CI/CD 

<img src="https://i.postimg.cc/W4sdcR1c/Captura-de-pantalla-2024-05-07-212529.png" alt="Captura de pantalla 2024-05-07 212529" style="width:50%;">

## Ship / Show / Ask

1. Ship: Se fusiona en la rama principal sin revisión
2. Show: Abre una petición de cambios para que sean revisados por CI pero se fusiona inmediatamente
3. Ask: Abre un PR para discutir los cambios antes de fusionarlos

<img src="https://i.postimg.cc/d11mvZVF/Captura-de-pantalla-2024-05-11-221916.png" alt="Captura de pantalla 2024-05-11 221916" style="width:50%;">

## Las reglas de Ship / Show / Ask

1. Tenemos un buen sistema de CI/CD
2. Confiamos en el equipo y existen buenas practicas de desarrollo. Pair programming, mob programming, seniority… y, sobre todo, existe responsabilidad. La persona se responsabiliza de decidir la categoría de su cambio.
3. Las revisiones de código no son requerimientos.
4. Las ramas son lo mas pequeñas posibles, tienen un tiempo de vida corto y siempre salen directamente desde la rama principal.
5. EL equipo ha sabido lidiar con el ego individual, las personas confían en el resto del equipo y las pruebas automáticas pasan.

<a href='https://github.com/user-attachments/assets/395b4159-2a02-4551-848f-1c6eecdf7884' target='_blank'><img src='https://github.com/user-attachments/assets/395b4159-2a02-4551-848f-1c6eecdf7884' alt='pull request image' style='width: 30%;' /></a>

<!---------------------------------------------------------------------------------------------------------->

# Clase 6 - Buenas prácticas en Git

## ¿Para qué sirven las buenas prácticas?

- Es un estándar manejado en la mayoría de equipos de desarrollo.
- Resolver conflictos o problemas durante el desarrollo es mas fácil
- Tu historial de commits es mas legible

## 1. ¿Cada cuánto debería hacer un commit?

### **A menudo**

 <img src="https://i.imgur.com/sVJ7jIs.gif" alt="Meme Git estilo Baki" style="width: 75%;">

Es mejor hacer commits pequeños, agrupando pequeñas mejoras o acciones, que un commit con todo lo que se quiere hacer.

Hacer commit a menudo no significa que debas hacer commits sin sentido.

## Escribir buenos commits

- Usar el verbo imperativo (Add, Change, Fix, Remove)
- No uses punto final ni puntos suspensivos en tus mensajes (a lo más usa la coma)
- Usa como máximo 50 caracteres para tu mensaje de commit
- Añade todo el contexto que se necesario en el cuerpo del commit (con reglas de puntuación)
- Considera usar utilidades para hacer commit
- Usa un prefijo para tus commits para hacerlos mas semánticos.

## Prefijos para commits

- **feat: Para una nueva característica para el usuario.**
- **fix**: para un bug que afecta al usuario.
- **perf**: para cambios que mejoran el rendimiento del sitio
- **build**: para cambios que mejoran el rendimiento del sitio.
- **ci**: para cambios en la integración continua.
- **docs**: para cambios en la documentación.
- **refactor**: para refactorización del código como cambios de nombre de variables o funciones.
- **style**: para cambios de formato, tabulaciones, espacios o puntos y coma, etc; no afectan al usuario.
- **test**: para test o refactorización de uno ya existente.

<img src="https://i.postimg.cc/mr5DKPcK/Captura-de-pantalla-2024-05-11-230400.png" alt="Captura de pantalla 2024-05-11 230400" style="width:50%;">

<table>
  <tr>
    <td width="55%">
      <h2>Escribir un buen nombre de rama</h2>
      <ul>
        <li>Sé consistente al nombrar tus ramas</li>
        <li>Usa el nombre de la acción que se realiza en la rama</li>
        <li>Usa los IDs de JIRA o el sistema de tickets que uses</li>
      </ul>
    </td>
    <td>
      <img src="https://i.postimg.cc/43bP5TmK/Captura-de-pantalla-2024-05-11-230606.png" alt="Captura de pantalla" style="width:100%;">
    </td>
  </tr>
</table>

<a href='https://github.com/user-attachments/assets/01d70597-5711-4c95-8342-570397b9f2dc' target='_blank'><img src='https://github.com/user-attachments/assets/01d70597-5711-4c95-8342-570397b9f2dc' border='0' alt='Image' style='width: 35%;'/></a>

<!---------------------------------------------------------------------------------------------------------->

# Clase 7 - Deshacer cambios

## ¿En qué casos deshacer cambios?

- Dejo de funcionar el proyecto.
- Queremos recuperar una parte del código que eliminamos.
- Queremos recuperar archivos que eliminamos.

## Comandos destructivos y no destructivos

Los comandos destructivos afectan el historial de commits realizado, sin embargo los comandos no destructivos trabajan en base al historial sin afectarlo.

### git reset

<a href='https://postimages.org/' target='_blank'><img src='https://i.postimg.cc/2SNmwftD/Captura-de-pantalla-2025-05-09-210841.png' border='0' alt='Captura-de-pantalla-2025-05-09-210841'/></a>

posee 2 opciones

- **soft**: Mantiene los cambios que ocurrieron antes de hacer commit desde donde apuntaba.
    - **`git reset --soft`**. Este comando se utiliza para deshacer cambios en el área de preparación (index) mientras se mantienen los cambios en el directorio de trabajo.
    - **`git reset --soft HEAD~<N>`** Deshace los últimos N commits sin borrar los cambios en tus archivos.
    - **`git reset --soft <SHA>`** Deshace cambios hasta un commit específico sin eliminar los cambios en tus archivos, dejándolos listos para ser confirmados nuevamente.
- **hard**: Descartar los cambios
    - **`git reset --hard`** se utiliza para deshacer los cambios en el directorio de trabajo y en el área de preparación (index), restableciendo el árbol de trabajo al estado del último commit. Esto significa que todos los cambios que no hayan sido confirmados se perderán permanentemente.
    - **`git reset --hard HEAD~<N>`** Deshace los últimos N commits y borra los cambios en tus archivos, restaurando el árbol de trabajo al estado en el que estaba antes de esos commits.
    - **`git reset --hard <SHA>`**Borras la historia de tu repositorio hasta un punto específico, como si usaras un borrador para retroceder y eliminar todo lo que ocurrió después de ese punto.

### git revert

<a href="https://postimages.org/" target="_blank"><img src="https://i.postimg.cc/nhFSZRjm/Captura-de-pantalla-2025-05-09-210624.png" alt="Captura de pantalla 2025-05-09 210624" style="width:40%;"></a>

Revierte los cambios que un commit introdujo, y crea un nuevo commit con los cambios revertidos.

- **`git revert <hash_del_commit>`** Se utiliza para deshacer cambios específicos realizados en un commit anterior creando un nuevo commit que revierte esos cambios. Es seguro de usar en repositorios compartidos porque no modifica la historia existente; en su lugar, crea un nuevo commit que deshace los cambios.
    - **`git revert HEAD~<N>`**Deshace los últimos N commits de manera segura, creando nuevos commits que revierten los cambios introducidos en esos commits específicos.
    - **`git revert <SHA>`** Deshace los cambios introducidos en un commit específico identificado por el hash **`<SHA>`**, creando un nuevo commit que revierte esos cambios.

### git checkout

Nos permite recuperar código especifico de commits. Te permite cambiar entre diferentes ramas, moverte hacia atrás y hacia adelante en la historia del repositorio, y deshacer cambios en tus archivos.

- **`git checkout HEAD~<N>`** Te permite volver al estado del proyecto en un commit específico anterior a los últimos N commits.
- **`git checkout <SHA>`** Te permite moverte a un commit específico identificado por su hash **`<SHA>`.**

<img src="https://github.com/user-attachments/assets/a1c50544-282e-4fc3-b925-8e608d49c14a" alt="GIF" style="width: 15%;" />
<!------------------------------------------------------------------->

# Clase 8 - Hooks, Alias y Trucos de Git

## ¿Qué es un Hook?

<img src="https://i.postimg.cc/1tMw0QrR/git-hooks.jpg" alt="git-hooks" width="600">

- Un hook, o un punto de enganche, es la posibilidad de ejecutar una acción o script cada vez que ocurre un evento determinado de Git.
- Hooks del lado del cliente
- Hooks del lado del servidor

## Hooks del lado del cliente

<img src="https://i.postimg.cc/1t4wKdCp/Captura-de-pantalla-2025-05-09-214715.png" alt="Captura-de-pantalla-2025-05-09-214715" width="800">

Sólo afectan al repositorio local que los contiene.

- **pre-commit**
    - Podrías comprobar si se esta intentando hacer un commit de demasiados archivos.
    - Puede ser un buen sitio para ejecutar el linter sobre los archivos que han sido modificados.
- **prepare-commit-msg**
    - Para modificar el mensaje del commit o añadir cualquier información extra.
- **commit-msg**
    - Es el sitio perfecto para hacer todas las comprobaciones pertinentes del mensaje
- **post-commit**
    - Su uso principal es la de notificar por Slack
- **pre-push**
    - Para ejecutar una bateria de test
- **post-checkout y post-merge**
    - Permite limpiar el directorio de trabajo, tras realizar un checkout, o el de limpiar las ramas que ya no se usan tras realizar un merge.

## Hooks del lado del servidor

<img src="https://i.postimg.cc/3w5cVX54/Captura-de-pantalla-2025-05-09-214609.png" alt="Captura-de-pantalla-2025-05-09-214609" width="600">

- **pre-receive**
    - Para comprobar que los commits que se quiere guardar estan bien formados.
    - Verificar que el usuario que intenta grabar los commits tiene los permisos necesarios para hacerlo
- **update**
    - Puedes evitar de una forma granular cada actualizacion
- **post-receive**
    - Enviar un correo a todos los usuarios del repositorio que se han grabado nuevos cambios en el repositorio remoto
    - Reflejar un una UI las nuevas referencias, ramas o commits disponibles.

## Creando un hook

Para crear un propio hook solo se tiene que crear un archivo nuevo nombre-del-hook en la carpeta .git/hooks y en el poner el código que quieras que se ejecute

Puedes usar todo tipo de interpretes de lenguaje de programación como bash, node, python, perl, etc.

## ¿Qué es un Alias?

- Los alias permiten definir una serie de comandos que pueden ser usados en lugar de los nombre completos.

<a href='https://postimages.org/' target='_blank'><img src='https://i.postimg.cc/8zCyBm3R/Captura-de-pantalla-2024-05-11-235015.png' border='0' alt='Captura-de-pantalla-2024-05-11-235015'/></a>

## Creando mi primer alias

Git te permite crear tu propio alias facilmente para comandos que usas habitualmente en tu proyecto con este sistema de control de versiones.

`git config --global alias.[nombre-del-alias] "comando a ejecutar"`

## Trucos en Git

### Guarda tus cambios temporalmente

`git stash`
`git stash -u
git stash pop`

### Aplicar cambios de commits en especifico

`git cherry-pick <SHA>`

### Detectar qué commit es el que ha introducido un bug

`git bisect`
`git bisect start
git bisect bad
git bisect good
git bisect reset`

### Cambiar el nombre de un commit

`git commit --ammend -m <descripcion commit>`

### Recuperar un archivo en concreto de otra rama o commit

`git checkout <SHA> <archivo>`

## Comandos

<img src="https://github.com/user-attachments/assets/69fb01b3-78ad-4d75-840d-dfa0ffc549e7" alt="Imagen" style="width: 30%;" />

comandos mencionados de la clase 8

- `git config --global alias.[nombre-del-alias] "comando a ejecutar"`: Crea un alias para un comando de Git, facilitando su uso en el futuro.
- `git stash`: Guarda temporalmente tus cambios actuales, permitiéndote volver a un estado limpio de tu repositorio.
- `git stash -u`: Guarda también archivos no seguidos (no versionados) en el stash.
- `git stash pop`: Aplica los cambios guardados en el stash y elimina el stash.
- `git cherry-pick <SHA>`: Aplica un commit específico de otra rama al estado actual de tu rama.
- `git bisect`: Ayuda a encontrar el commit que introdujo un error, realizando una búsqueda binaria entre buenos y malos commits.
- `git bisect start`: Inicia el proceso de bisecting para encontrar el commit problemático.
- `git bisect bad`: Marca el commit actual como "malo", es decir, contiene el error.
- `git bisect good`: Marca el commit actual como "bueno", es decir, no tiene el error.
- `git bisect reset`: Resetea el proceso de bisecting y regresa al estado original.
- `git commit --ammend -m <descripcion commit>`: Modifica el último commit, permitiéndote cambiar el mensaje o agregar cambios.
- `git checkout <SHA> <archivo>`: Recupera un archivo específico de un commit anterior o de otra rama.

Fin.
