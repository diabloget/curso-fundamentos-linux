---
theme: default
title: Fundamentos de Linux - Clase 4
drawings:
  persist: false
transition: fade
fonts:
  sans: Inter
  mono: JetBrains Mono
---

<div class="deck-frame">
  <div class="red-title-bar"><img class="title-bar-icon" src="/img/RocketGirlsLogo.png" alt="Rocket Girls" />Clase 4 · Fundamentos de Linux</div>
  <div class="course-tag">Rocket Tech Academy</div>
  <div class="hero-row">
    <div class="hero-main">
      <h1 class="hero-title">Usuarios y <span>permisos</span></h1>
      <p class="subtitle">Entender quién puede leer, modificar o ejecutar archivos.</p>
      <div class="agenda">
        <div class="agenda-item">Usuarios, grupos y creación de cuentas</div>
        <div class="agenda-item">El usuario <code class="cmd-pill">root</code> y privilegios con <code class="cmd-pill">sudo</code></div>
        <div class="agenda-item">Propietarios y permisos de archivos</div>
        <div class="agenda-item">Cambiar permisos con <code class="cmd-pill">chmod</code></div>
        <div class="agenda-item">Cambiar propietario con <code class="cmd-pill">chown</code></div>
        <div class="agenda-item">Enlaces simbólicos y buenas prácticas</div>
      </div>
    </div>
  </div>
  <div class="footer-line"></div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Identidad</div>
  <h2 class="slide-title">¿Quién está usando el sistema?</h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">whoami</span></div>
      <div class="term-line term-out">diblo</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">id</span></div>
      <div class="term-line term-out">uid=1000(diblo) gid=1000(diblo) grupos=1000(diblo),10(wheel)</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota</strong> Linux no trabaja exclusivamente con «personas». Los usuarios también existen para servicios o tareas del sistema.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Grupos</div>
  <h2 class="slide-title">Usuarios dentro de grupos</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">groups</code></h3>
      <ul>
        <li>Muestra los grupos a los que pertenece un usuario.</li>
        <li class="example-line">Ejemplo <code class="code-pill">groups diblo</code></li>
        <li>Los grupos permiten compartir permisos entre varias cuentas.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">id</code></h3>
      <ul>
        <li>Muestra el identificador del usuario y sus grupos.</li>
        <li class="example-line">Ejemplo <code class="code-pill">id diblo</code></li>
        <li>UID identifica usuarios. GID identifica grupos.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Administración</div>
  <h2 class="slide-title">Crear usuarios y asignar grupos</h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">sudo</span> <span class="term-flag">useradd -m priscilla</span></div>
      <div class="term-line term-out">Crea el usuario y su directorio Home</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">sudo</span> <span class="term-flag">usermod -aG proyecto priscilla</span></div>
      <div class="term-line term-out">Agrega priscilla al grupo proyecto</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota</strong> Al ejecutar estos comandos en una computadora personal o servidor se modifica la configuración del sistema operativo. Aunque algunos ejemplos sean pequeños, crear usuarios o cambiar permisos puede abrir una vulnerabilidad que permita a otra persona o programa acceder a archivos sensibles o utilizar <code class="code-pill">sudo</code>.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Privilegios</div>
  <h2 class="slide-title">El usuario <code class="cmd-pill">root</code> y <code class="cmd-pill">sudo</code></h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">root</code></h3>
      <ul>
        <li>Es la cuenta administrativa principal del sistema.</li>
        <li>Puede modificar casi cualquier archivo o configuración.</li>
        <li>No es recomendable trabajar siempre como root.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="cmd-pill">sudo</code></h3>
      <ul>
        <li>Ejecuta temporalmente un comando con permisos elevados.</li>
        <li class="example-line">Ejemplo <code class="code-pill">sudo dnf install tree</code></li>
        <li>Permite ejecutar temporalmente un comando como <code class="cmd-pill">root</code>, si la configuración de <code class="cmd-pill">sudo</code> lo autoriza.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Propiedad</div>
  <h2 class="slide-title">¿Quién es dueño de un archivo?</h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">-l reporte.txt</span></div>
      <div class="term-line term-out">-rw-r--r-- 1 diblo diblo 0 jul 13 20:15 reporte.txt</div>
    </div>
  </div>
  <div class="topic-list">
    <div class="topic-item"><code class="code-pill">diblo</code><span class="note">Primer nombre después del tamaño de enlaces. Representa al usuario propietario.</span></div>
    <div class="topic-item"><code class="code-pill">diblo</code><span class="note">Segundo nombre. Representa al grupo propietario.</span></div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Permisos</div>
  <h2 class="slide-title">Lectura, escritura y ejecución</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case"><code class="code-pill">rwx</code></h3>
      <ul>
        <li><code class="code-pill">r</code> permite leer.</li>
        <li><code class="code-pill">w</code> permite modificar.</li>
        <li><code class="code-pill">x</code> permite ejecutar o entrar a un directorio.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case"><code class="code-pill">rwx r-x r--</code></h3>
      <ul>
        <li>Primer bloque para el usuario propietario.</li>
        <li>Segundo bloque para el grupo propietario.</li>
        <li>Tercer bloque para los demás usuarios.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Cambiar permisos</div>
  <h2 class="slide-title">El comando <code class="cmd-pill">chmod</code></h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">chmod</span> <span class="term-flag">u+x script.sh</span></div>
      <div class="term-line term-out">Agrega ejecución al usuario propietario</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">chmod</span> <span class="term-flag">g-w reporte.txt</span></div>
      <div class="term-line term-out">Quita escritura al grupo propietario</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota</strong> Usamos <code class="code-pill">u</code>, <code class="code-pill">g</code>, <code class="code-pill">o</code> o <code class="code-pill">a</code> junto con <code class="code-pill">+</code>, <code class="code-pill">-</code> o <code class="code-pill">=</code>.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Permisos numéricos</div>
  <h2 class="slide-title">El modo <code class="code-pill">644</code> y <code class="code-pill">755</code></h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case">Valores</h3>
      <ul>
        <li><code class="code-pill">r = 4</code></li>
        <li><code class="code-pill">w = 2</code></li>
        <li><code class="code-pill">x = 1</code></li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case">Ejemplos del día a día</h3>
      <ul>
        <li><code class="code-pill">644</code> para archivos de texto comunes.</li>
        <li><code class="code-pill">755</code> para scripts o directorios compartidos.</li>
        <li class="example-line">Ejemplo <code class="code-pill">chmod 644 reporte.txt</code></li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Cambiar dueño</div>
  <h2 class="slide-title">El comando <code class="cmd-pill">chown</code></h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">sudo</span> <span class="term-flag">chown priscilla reporte.txt</span></div>
      <div class="term-line term-out">Cambia el usuario propietario</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">sudo</span> <span class="term-flag">chown priscilla:proyecto reporte.txt</span></div>
      <div class="term-line term-out">Cambia usuario y grupo propietario</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota</strong> Cambiar propietarios suele requerir privilegios administrativos.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Atajos</div>
  <h2 class="slide-title">Enlaces simbólicos (<span>symlinks</span>)</h2>
  <div class="topic-list">
    <div class="topic-item">¿Qué es?<span class="note">Un archivo especial que apunta hacia otro archivo o directorio, parecido a un acceso directo. Se crea con <code class="code-pill">ln -s</code>.</span></div>
    <div class="topic-item">¿Para qué sirve?<span class="note">Permite acceder al mismo archivo desde otra ruta sin duplicar su contenido.</span></div>
    <div class="topic-item">¿Cómo se usa?<span class="note"><code class="code-pill">ln -s destino nombre_enlace</code> crea el enlace y luego puede utilizarse como si fuera el archivo original.</span></div>
  </div>
  <p class="mini-note"><strong>Nota</strong> El enlace apunta al archivo original. No duplica su contenido.</p>
</div>
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Atajos</div>
  <h2 class="slide-title">Qué pasa al usar o borrar un symlink</h2>
  <div class="two-col">
    <div class="col-card">
      <h3 class="plain-case">Usarlo</h3>
      <ul>
        <li>Leer el enlace normalmente lee el archivo original.</li>
        <li class="example-line">Ejemplo <code class="code-pill">cat acceso_reporte.txt</code></li>
        <li>Si el destino no existe, el enlace queda roto.</li>
      </ul>
    </div>
    <div class="col-card">
      <h3 class="plain-case">Borrarlo</h3>
      <ul>
        <li>Eliminar el enlace no elimina el archivo original.</li>
        <li class="example-line">Ejemplo <code class="code-pill">rm acceso_reporte.txt</code></li>
        <li>Solo se borra el enlace simbólico (symlink).</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Seguridad</div>
  <h2 class="slide-title">Buenas prácticas al trabajar con permisos</h2>
  <div class="topic-list">
    <div class="topic-item"><code class="cmd-pill">sudo</code> solo cuando sea necesario<span class="note">Si un comando funciona sin privilegios elevados, mejor ejecutarlo como usuario normal.</span></div>
    <div class="topic-item">Evitar <code class="code-pill">chmod 777</code><span class="note">Da permisos de lectura, escritura y ejecución a todos.</span></div>
    <div class="topic-item">Principio del mínimo privilegio<span class="note">Cada usuario o proceso debería tener solo los permisos necesarios para su tarea.</span></div>
  </div>
</div>

---

<div class="closing-slide">
  <div class="closing-title">¿<span>Preguntas</span>?</div>
  <div class="closing-sub">Rocket Tech Academy · Fundamentos de Linux · Clase 4</div>
</div>
