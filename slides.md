---
theme: default
title: Fundamentos de Linux - Clase 5
drawings:
  persist: false
transition: fade
fonts:
  sans: Inter
  mono: JetBrains Mono
---

<div class="deck-frame">
  <div class="red-title-bar"><img class="title-bar-icon" src="/public/img/RocketGirlsLogo.png" alt="Rocket Girls" />Clase 5 · Fundamentos de Linux</div>
  <div class="course-tag">Rocket Tech Academy</div>
  <div class="hero-row">
    <div class="hero-main">
      <h1 class="hero-title">Sistema y <span>procesamiento</span> de entradas y salidas</h1>
      <p class="subtitle">Explorar la estructura de Linux y combinar comandos desde la terminal.</p>
      <div class="agenda">
        <div class="agenda-item">Filesystem Hierarchy y directorios principales</div>
        <div class="agenda-item">Redirecciones (<code class="cmd-pill">&gt;</code>, <code class="cmd-pill">&gt;&gt;</code> y <code class="cmd-pill">&lt;</code>)</div>
        <div class="agenda-item">Pipes y composición de comandos</div>
        <div class="agenda-item">Búsqueda con <code class="cmd-pill">grep</code></div>
        <div class="agenda-item">Introducción a expresiones regulares</div>
      </div>
    </div>
  </div>
  <div class="footer-line"></div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Filesystem</div>
  <h2 class="slide-title">¿Dónde viven los archivos en Linux?</h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash - konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">/</span></div>
      <div class="term-line term-out">bin  etc  home  tmp  usr  var  opt  root</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota:</strong> Recordemos que todo comienza desde el directorio raíz <code class="code-pill">/</code>.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Directorios</div>
  <h2 class="slide-title">Directorios importantes</h2>
  <div class="topic-list">
    <div class="topic-item"><code class="code-pill">/home</code><span class="note">Archivos personales de los usuarios.</span></div>
    <div class="topic-item"><code class="code-pill">/etc</code><span class="note">Configuración del sistema y de muchos servicios.</span></div>
    <div class="topic-item"><code class="code-pill">/var</code><span class="note">Logs y datos que cambian con frecuencia.</span></div>
    <div class="topic-item"><code class="code-pill">/usr/bin</code><span class="note">Programas disponibles para los usuarios.</span></div>
    <div class="topic-item"><code class="code-pill">/tmp</code><span class="note">Archivos temporales. Su contenido puede borrarse automáticamente.</span></div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Entradas y salidas</div>
  <h2 class="slide-title">Tipos de salidas</h2>
  <div class="topic-list">
    <div class="topic-item"><code class="cmd-pill">stdin</code><span class="note">Entrada estándar. Normalmente viene del teclado o de otro comando.</span></div>
    <div class="topic-item"><code class="cmd-pill">stdout</code><span class="note">Salida estándar. Normalmente se muestra en la terminal.</span></div>
    <div class="topic-item"><code class="cmd-pill">stderr</code><span class="note">Salida de error. Se usa para mensajes de error o advertencias.</span></div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Redirecciones</div>
  <h2 class="slide-title">Redireccionar entradas y salidas</h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash - konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">-l &gt; archivos.txt</span></div>
      <div class="term-line term-out">Crea o reemplaza el contenido del archivo.</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">echo</span> <span class="term-flag">"nuevo" &gt;&gt; archivos.txt</span></div>
      <div class="term-line term-out">Agrega contenido al final.</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">wc</span> <span class="term-flag">-l &lt; archivos.txt</span></div>
      <div class="term-line term-out">Usa el archivo como entrada.</div>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Pipes</div>
  <h2 class="slide-title">Conectar comandos con <span>|</span></h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash - konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">-l | grep reporte</span></div>
      <div class="term-line term-out">Envía la salida de ls como entrada de grep.</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">cat</span> <span class="term-flag">usuarios.txt | sort | uniq</span></div>
      <div class="term-line term-out">Ordena y elimina líneas repetidas.</div>
    </div>
  </div>
  <p class="mini-note"><strong>Nota:</strong> El pipe conecta la salida o entrada de distintos comandos.</p>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Búsqueda</div>
  <h2 class="slide-title">Buscar texto con <code class="cmd-pill">grep</code></h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash - konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">grep</span> <span class="term-flag">"error" reporte.txt</span></div>
      <div class="term-line term-out">Busca líneas que contienen error.</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">grep</span> <span class="term-flag">-i "error" reporte.txt</span></div>
      <div class="term-line term-out">Ignora mayúsculas y minúsculas.</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">grep</span> <span class="term-flag">-n "error" reporte.txt</span></div>
      <div class="term-line term-out">Muestra el número de línea.</div>
    </div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Expresiones regulares</div>
  <h2 class="slide-title">Patrones básicos con <code class="cmd-pill">grep</code></h2>
  <div class="topic-list">
    <div class="topic-item"><code class="code-pill">grep "^reporte" *.txt</code><span class="note">Busca líneas que empiezan con reporte.</span></div>
    <div class="topic-item"><code class="code-pill">grep "12$" *.txt</code><span class="note">Busca líneas que terminan en 12.</span></div>
    <div class="topic-item"><code class="code-pill">grep "reporte[0-9]" *.txt</code><span class="note">Busca reporte seguido de un dígito.</span></div>
    <div class="topic-item"><code class="code-pill">grep -E "error|warning" log.txt</code><span class="note">Busca error o warning usando patrones extendidos.</span></div>
  </div>
</div>

---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Composición</div>
  <h2 class="slide-title">Ejemplos útiles de composición</h2>
  <div class="term-window">
    <div class="term-header">
      <div class="term-title">bash - konsole</div>
      <div class="term-controls">
        <div class="term-btn">−</div>
        <div class="term-btn">▢</div>
        <div class="term-btn close">×</div>
      </div>
    </div>
    <div class="term-body">
      <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">ls</span> <span class="term-flag">*.txt | wc -l</span></div>
      <div class="term-line term-out">Cuenta archivos de texto.</div>
      <div class="term-line" style="margin-top:10px"><span class="term-prompt">❯</span> <span class="term-cmd">grep</span> <span class="term-flag">-r "error" /var/log | less</span></div>
      <div class="term-line term-out">Busca errores en logs y permite leerlos por páginas.</div>
    </div>
  </div>
</div>

---

<div class="closing-slide">
  <div class="closing-title">¿<span>Preguntas</span>?</div>
  <div class="closing-sub">Rocket Tech Academy · Fundamentos de Linux · Clase 5</div>
</div>
