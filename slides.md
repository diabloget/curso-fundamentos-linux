---
theme: default
title: Fundamentos de Linux - Clase 2
drawings:
  persist: false
transition: fade
fonts:
  sans: Inter
  mono: JetBrains Mono
---

<div class="deck-frame">
  <div class="red-title-bar"><img class="title-bar-icon" src="/public/img/RocketGirlsLogo.png" alt="Rocket Girls" />Clase 2 · Fundamentos de Linux</div>
  <div class="course-tag">Rocket Tech Academy</div>
  <div class="hero-row">
    <div class="hero-main">
      <h1 class="hero-title">Navegación y <span>la terminal</span></h1>
      <p class="subtitle">Moverse entre carpetas (directorios), ver y buscar archivos desde una terminal.</p>
      <div class="agenda">
        <div class="agenda-item">La terminal y la sintaxis de los comandos</div>
        <div class="agenda-item">Ubicarse y moverse a través de directorios (<code class="cmd-pill">pwd</code> y <code class="cmd-pill">cd</code>)</div>
        <div class="agenda-item">Listar archivos en un directorio</div>
        <div class="agenda-item">Ayuda y documentación (<code class="cmd-pill">man</code> y <code class="cmd-pill">--help</code>)</div>
      </div>
    </div>
  </div>
  <div class="footer-line"></div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">¿Cómo se arma un comando?</div>
  <h2 class="slide-title">La sintaxis y tipos de comandos</h2>
  <div class="two-col">
    <div class="col-card">
      <h3>Sintaxis</h3>
      <ul>
        <li><code class="code-pill">comando [flags] [argumentos]</code></li>
        <li class="example-line">Ejemplo: <code class="code-pill">ls -la /home</code></li>
      </ul>
    </div>
    <div class="col-card">
      <h3>Tipos de comandos</h3>
      <ul>
        <li>Internos (built-in): son parte del propio shell.</li>
        <li class="example-line">Ejemplo: <code class="cmd-pill">cd</code></li>
        <li>Externos: son programas independientes.</li>
        <li class="example-line">Ejemplo: <code class="cmd-pill">ls</code></li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Organización</div>
  <h2 class="slide-title">El sistema de archivos es un solo árbol</h2>
  <p class="slide-sub">Linux organiza todo bajo una raíz: <code class="code-pill">/</code>. No usa letras como <code class="code-pill">C:</code> o <code class="code-pill">D:</code>.</p>
  <div class="two-col">
    <div class="col-card">
      <h3>En Windows</h3>
      <ul>
        <li>Cada disco suele aparecer con una letra.</li>
        <li>Ejemplo: <code class="code-pill">C:\Usuarios</code></li>
        <li>Ejemplo: <code class="code-pill">D:\Juegos</code></li>
      </ul>
    </div>
    <div class="col-card">
      <h3>En Linux</h3>
      <ul>
        <li>Todo cuelga desde <code class="code-pill">/</code>.</li>
        <li>Un disco o partición puede “montarse” dentro del árbol.</li>
        <li><code class="code-pill">/</code> y <code class="code-pill">/home</code> pueden estar en particiones diferentes.</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Ubicación</div>
  <h2 class="slide-title"><code class="cmd-pill">pwd</code>: ¿Contexto? ¿Dónde estoy?</h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash — konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body pwd-demo">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">pwd</span></div>
      <div v-click="1" class="enter-key">Enter ↵</div>
      <div v-click="2" class="term-line term-out">/home/darobles</div>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Desplazamiento entre directorios</div>
  <h2 class="slide-title">Ruta absoluta vs Ruta relativa</h2>
  <p class="slide-sub">Si empieza con <code class="code-pill">/</code>, es absoluta. Caso contrario, se considera relativa.</p>
  <div class="two-col">
    <div class="col-card">
      <h3>Ruta absoluta</h3>
      <ul>
        <li>Empieza con <code class="code-pill">/</code></li>
        <li>Esta siempre apunta a un mismo lugar, no importa en qué directorio se esté</li>
        <li>Ejemplo: <code class="code-pill">cd /home/darobles/Documentos</code></li>
      </ul>
    </div>
    <div class="col-card">
      <h3>Ruta relativa</h3>
      <ul>
        <li>No empieza con <code class="code-pill">/</code></li>
        <li>Directorio actual sí es relevante</li>
        <li><code class="code-pill">.</code> es aquí mismo, <code class="code-pill">..</code> es un directorio atrás</li>
      </ul>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Listar contenido</div>
  <h2 class="slide-title">El comando <code class="cmd-pill">ls</code></h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span></div>
      <div class="term-line term-out">Documentos  Descargas  Imagenes</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">-la</span></div>
      <div class="term-line term-out">drwxr-xr-x  darobles darobles  .config</div>
      <div class="term-line term-out">-rw-r--r--  darobles darobles  .bashrc</div>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Árbol de directorios</div>
  <h2 class="slide-title">El comando <code class="cmd-pill">tree</code></h2>
  <p class="slide-sub"><code class="cmd-pill">tree</code> muestra carpetas y archivos como un árbol visual.</p>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">tree</span> <span class="term-flag">Documentos</span></div>
      <div class="term-line term-out">Documentos</div>
      <div class="term-line term-out">├── tareas</div>
      <div class="term-line term-out">│   └── linux.txt</div>
      <div class="term-line term-out">└── notas.txt</div>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Convenciones</div>
  <h2 class="slide-title">Archivos <span>ocultos</span> y el directorio <span>Home</span></h2>
  <div class="topic-list">
    <div class="topic-item">¿Su nombre empieza con <code class="code-pill">.</code>?<span class="note">Todo archivo o carpeta que empieza con <code class="code-pill">.</code> está oculto por convención. Ejemplo: <code class="code-pill">.gitignore</code></span></div>
    <div class="topic-item"><code class="code-pill">~</code><span class="note">Atajo para tu directorio Home. En inglés se le suele llamar <em>tilde</em>. Equivale a <code class="code-pill">/home/usuario</code></span></div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Búsqueda por patrón</div>
  <h2 class="slide-title">Comodín en los directorios (<span>wildcards</span>)</h2>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">*.txt</span></div>
      <div class="term-line term-out">notas.txt  tarea1.txt</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">tarea?.txt</span></div>
      <div class="term-line term-out">tarea1.txt</div>
    </div>
  </div>
  <div class="callout"><strong>Resumen:</strong> <code>*</code> reemplaza a cualquier cantidad de caracteres, <code>?</code> reemplaza exactamente uno.</div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Ayudas disponibles</div>
  <h2 class="slide-title">Comando <code class="cmd-pill">man</code> y el flag <code class="cmd-pill">--help</code></h2>
  <p class="slide-sub"><code class="cmd-pill">man</code> es documentación, <code class="cmd-pill">--help</code> es una guía o resumen más corto.</p>
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
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">man</span> <span class="term-flag">ls</span></div>
      <div class="term-line term-out">Abre el manual completo del comando</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">--help</span></div>
      <div class="term-line term-out">Muestra un resumen rápido de flags</div>
    </div>
  </div>
</div>

---

<div class="closing-slide">
  <div class="closing-title">¿<span>Preguntas</span>?</div>
  <div class="closing-sub">Rocket Tech Academy · Fundamentos de Linux · Clase 2</div>
</div>
