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
      <img src="https://i.postimg.cc/vZDjL204/a2c1165235c53e8695b8bde7d9ae8366.jpg" width="300">
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
      <img src="https://media.giphy.com/media/JIX9t2j0ZTN9S/giphy.gif" alt="Bongo Cat" width="180">
    </td>
  </tr>
</table>

<img src="https://i.imgur.com/sVJ7jIs.gif" alt="Meme Git estilo Baki" />
