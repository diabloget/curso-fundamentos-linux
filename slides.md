---
theme: default
title: Fundamentos de Linux - Clase 3
drawings:
  persist: false
transition: fade
fonts:
  sans: Inter
  mono: JetBrains Mono
---

<div class="deck-frame">
  <div class="red-title-bar"><img class="title-bar-icon" src="/public/img/RocketGirlsLogo.png" alt="Rocket Girls" />Clase 3 · Fundamentos de Linux</div>
  <div class="course-tag">Rocket Tech Academy</div>
  <div class="hero-row">
    <div class="hero-main">
      <h1 class="hero-title">Manipulación de <span>archivos</span></h1>
      <p class="subtitle">Crear, copiar, mover, eliminar y buscar archivos desde la terminal.</p>
      <div class="agenda">
        <div class="agenda-item">Creación de archivos y directorios (<code class="cmd-pill">mkdir</code> y <code class="cmd-pill">touch</code>)</div>
        <div class="agenda-item">Copiar y mover archivos (<code class="cmd-pill">cp</code> y <code class="cmd-pill">mv</code>)</div>
        <div class="agenda-item">Eliminar archivos y directorios (<code class="cmd-pill">rm</code> y <code class="cmd-pill">rmdir</code>)</div>
        <div class="agenda-item">Ver y editar el contenido de un archivo</div>
        <div class="agenda-item">Buscar archivos (<code class="cmd-pill">locate</code> y <code class="cmd-pill">find</code>)</div>
        <div class="agenda-item">Agrupar, comprimir y enlazar archivos</div>
      </div>
    </div>
  </div>
  <div class="footer-line"></div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Crear</div>
  <h2 class="slide-title">Creación de archivos y directorios</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">mkdir</code></h3>
      <ul>
        <li>Crea un directorio nuevo.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">mkdir semana3</code></li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">touch</code></h3>
      <ul>
        <li>Crea un archivo vacío, o actualiza su fecha si ya existe.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">touch semana3.txt</code></li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Duplicar y reubicar</div>
  <h2 class="slide-title">Copiar y mover archivos</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">cp</code></h3>
      <ul>
        <li>Copia un archivo o carpeta a otro lugar.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">cp semana3.txt respaldo.txt</code></li>
        <li>El archivo original se mantiene igual.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">mv</code></h3>
      <ul>
        <li>Mueve un archivo o carpeta a otro lugar.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">mv semana3.txt Documentos/</code></li>
        <li>También sirve para renombrar, es la misma operación.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Eliminar</div>
  <h2 class="slide-title">Eliminar archivos y directorios</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">rm</code></h3>
      <ul>
        <li>Elimina archivos.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">rm semana3.txt</code></li>
        <li>No existe una papelera de reciclaje en la terminal.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">rmdir</code></h3>
      <ul>
        <li>Elimina un directorio, solo si está vacío.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">rmdir semana3</code></li>
        <li>Si tiene contenido adentro, no lo va a eliminar por defecto.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Lectura</div>
  <h2 class="slide-title">Ver el contenido de un archivo</h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash — konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">cat</span> <span class="term-flag">notas.txt</span></div>
      <div class="term-line term-out">Imprime todo el contenido</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">less</span> <span class="term-flag">notas.txt</span></div>
      <div class="term-line term-out">Muestra el contenido una página a la vez</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota:</strong> less es en sí mismo un lector, usa q para salir, f para avanzar y b para retroceder.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Editar</div>
  <h2 class="slide-title">¿Cómo se modifican los archivos?</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case">nano y Micro</h3>
      <ul>
        <li>Editores simples.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">nano notas.txt</code></li>
        <li>Los atajos disponibles se muestran en pantalla.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case">vim</h3>
      <ul>
        <li>Editor más potente, con más funciones.</li>
        <li>Su curva de aprendizaje es más alta.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">vim notas.txt</code></li>
        <li>No es necesario dominarlo por ahora.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Búsqueda</div>
  <h2 class="slide-title">Buscar archivos en el sistema</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">locate</code></h3>
      <ul>
        <li>Busca pasiva o con caché.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">locate semana3.txt</code></li>
        <li>Rápido.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">find</code></h3>
      <ul>
        <li>Busca activa y actual.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">find . -name "*.txt"</code></li>
        <li>Lento.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">zip y tar</div>
  <h2 class="slide-title">Agrupar y comprimir archivos</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case">Agrupar</h3>
      <ul>
        <li>Junta varios archivos en uno solo.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">tar -cvf carpeta.tar carpeta/</code></li>
        <li>No implica reducción de tamaño.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case">Comprimir</h3>
      <ul>
        <li>Reduce el tamaño.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">zip -r carpeta.zip carpeta/</code></li>
        <li>Este puede tener una contraseña o clave de cifrado.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Atajos</div>
  <h2 class="slide-title">Enlaces simbólicos (<span>symlinks</span>)</h2>
  <div class="topic-list">
    <div class="topic-item">¿Qué es?<span class="note">Un archivo especial que apunta hacia otro archivo o carpeta, parecido a un acceso directo. Se crea con <code class="code-pill">ln -s</code></span></div>
    <div class="topic-item">¿Para qué sirve?<span class="note">Permite acceder al mismo archivo desde varias rutas distintas, sin duplicar su contenido</span></div>
    <div class="topic-item">¿Cómo se usa?<span class="note">Se crea con <code class="code-pill">ln -s semana3.txt acceso.txt</code> y ahora podemos usarlo comos si fuera el original <code class="code-pill">cat acceso.txt</code></span></div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Repositorios</div>
  <h2 class="slide-title">Cómo se distribuye el software en Linux</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case">Basadas en Debian o Ubuntu</h3>
      <ul>
        <li>Usan <code class="cmd-pill">apt</code> para instalar y actualizar programas.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">sudo apt install nombre-programa</code></li>
        <li class="example-line">Actualizar el sistema: <code class="code-pill">sudo apt update && sudo apt upgrade</code></li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case">Basadas en RedHat o Fedora</h3>
      <ul>
        <li>Usan <code class="cmd-pill">dnf</code>.</li>
        <li class="example-line">Ejemplo: <code class="code-pill">sudo dnf install nombre-programa</code></li>
        <li class="example-line">Actualizar el sistema: <code class="code-pill">sudo dnf upgrade</code></li>
      </ul>
    </div>
  </div>
  <p class="mini-note"><strong>Nota:</strong> Como se mencionó en la primera clase, si la distribución tiene un "papá" esta suele heredar sus repositorios y gestores de software, si no tienen un papá, suelen tener uno propio. Ejemplos de distribuciones que usan su propio gestor: Solus, Void Linux...</p>
</div>

---

<div class="closing-slide">
  <div class="closing-title">¿<span>Preguntas</span>?</div>
  <div class="closing-sub">Rocket Tech Academy · Fundamentos de Linux · Clase 3</div>
</div>