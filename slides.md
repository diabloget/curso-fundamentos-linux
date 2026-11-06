---
layout: none
theme: default
title: Fundamentos de Linux - Clase 1
drawings:
  persist: false
transition: fade
fonts:
  sans: Inter
  mono: JetBrains Mono
---

<div class="deck-frame">
  <div class="red-title-bar"><img class="title-bar-icon" src="/img/RocketGirlsLogo.png" alt="Rocket Girls" />Clase 1 - Fundamentos de Linux</div>
  <div class="course-tag">Rocket Tech Academy</div>
  <div class="hero-row">
    <div class="hero-main">
      <h1 class="hero-title">Primer contacto con <span>Linux</span></h1>
      <p class="subtitle">Software libre, distribuciones, entornos de práctica y primeros comandos desde la terminal.</p>
      <div class="agenda">
        <div class="agenda-item">¿Qué es Linux y dónde se usa?</div>
        <div class="agenda-item">Historia, distribuciones y arquitecturas</div>
        <div class="agenda-item">Gaming en Linux: SteamOS y Proton</div>
        <div class="agenda-item">Entornos de práctica y primer comando</div>
      </div>
    </div>
    <div class="hero-visual">
      <div class="profile-card">
        <img class="profile-photo" src="/img/perfil.png" alt="David Robles" />
        <div class="profile-name">Prof. David A. Robles Vargas</div>
        <div class="profile-role">Estudiante de Ciencias de la Computación y Guitarra Clásica</div>
        <div class="profile-institution">Instituto Tecnológico de Costa Rica</div>
        <div class="profile-contact">
          <div class="profile-contact-item"><div class="contact-icon" style="background-image:url('/icons/email.svg')"></div><span>darobles@proton.me</span></div>
          <div class="profile-contact-item"><div class="contact-icon" style="background-image:url('/icons/whatsapp.svg')"></div><span>86329326</span></div>
          <div class="profile-contact-item"><div class="contact-icon" style="background-image:url('/icons/signal.svg')"></div><span>darobles.49</span></div>
        </div>
      </div>
    </div>
  </div>
  <div class="corner-cut"></div>
  <div class="footer-line"></div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Historia - 1983 en adelante</div>
  <h2 class="slide-title">De un proyecto de estudiante a <span>todas partes</span></h2>
  <div class="timeline">
    <div class="timeline-item">
      <div class="timeline-year">1983</div>
      <div class="timeline-label">Richard Stallman funda el proyecto GNU</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">1991</div>
      <div class="timeline-label">Linus Torvalds publica el primer kernel Linux</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">Años 90</div>
      <div class="timeline-label">Se popularizan las distribuciones GNU/Linux</div>
    </div>
    <div class="timeline-item">
      <div class="timeline-year">2000–hoy</div>
      <div class="timeline-label">Linux llega a servidores, Android y la nube</div>
    </div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Para arrancar</div>
  <h2 class="slide-title">¿Qué es <span>Linux</span>, realmente?</h2>
  <p class="slide-sub">Linux es el núcleo. Una distribución añade las herramientas para usarlo.</p>
  <div class="topic-list">
    <div class="topic-item">Kernel<span class="note">Gestiona hardware, memoria y procesos.</span></div>
    <div class="topic-item">Arranque<span class="note">GRUB o systemd-boot cargan el sistema.</span></div>
    <div class="topic-item">Entorno de escritorio<span class="note">Interfaz gráfica como GNOME o KDE Plasma.</span></div>
    <div class="topic-item">Gestor de paquetes<span class="note">Instala y actualiza programas.</span></div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Módulo 1 - Distribuciones</div>
  <h2 class="slide-title">Un kernel, <span>muchos sabores</span></h2>
  <p class="slide-sub">Cada distribución combina el kernel con sus propias herramientas.</p>
  <div class="logo-grid">
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/ubuntu.svg')"></div><span>Ubuntu</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/linuxmint.svg')"></div><span>Linux Mint</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/zorinos.svg')"></div><span>Zorin OS</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/fedora.svg')"></div><span>Fedora</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/debian.svg')"></div><span>Debian</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/redhat.svg')"></div><span>RHEL</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/cachyos.svg')"></div><span>CachyOS</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/bazzite.svg')"></div><span>Bazzite</span></div>
    <div class="logo-chip"><div class="logo-icon" style="background-image:url('/icons/steamos.svg')"></div><span>SteamOS</span></div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Cómo elegir una distro</div>
  <h2 class="slide-title">Modelos de lanzamiento y <span>arquitecturas</span></h2>
  <div class="two-col">
    <div class="col-card">
      <h3>Modelos de lanzamiento</h3>
      <ul>
        <li>Versiones fijas</li>
        <li>LTS (soporte a largo plazo)</li>
        <li>Rolling release</li>
      </ul>
    </div>
    <div class="col-card">
      <h3>Arquitecturas</h3>
      <ul>
        <li>x86 (32 bits) y x86_64 (64 bits)</li>
        <li>ARM32 y ARM64</li>
        <li>RISC-V y otras</li>
      </ul>
    </div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Presencia actual</div>
  <h2 class="slide-title">¿En dónde vive <span>Linux</span> hoy?</h2>
  <p class="slide-sub">En muchos más lugares de los que parece.</p>
  <div class="topic-list">
    <div class="topic-item">Servidores y la nube<span class="note">Muy usado en servidores y servicios en la nube</span></div>
    <div class="topic-item">Android<span class="note">Android utiliza el kernel Linux</span></div>
    <div class="topic-item">Sistemas embebidos<span class="note">Routers, TVs, electrodomésticos</span></div>
    <div class="topic-item">Clústeres de alto rendimiento (HPC)<span class="note">Linux domina las supercomputadoras del TOP500</span></div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">¿Diferentes sistemas operativos?</div>
  <h2 class="slide-title"><span>Linux</span> y <span>BSD</span></h2>
  <div class="compare-grid">
    <div class="compare-card">
      <span class="tag">Licencia GPL</span>
      <h3>Linux</h3>
      <ul>
        <li>Copyleft al distribuir versiones modificadas</li>
        <li>Enorme ecosistema de distribuciones</li>
      </ul>
    </div>
    <div class="compare-card">
      <span class="tag">Licencia BSD</span>
      <h3>FreeBSD y familia</h3>
      <ul>
        <li>Permite distribuir cambios sin publicar el código</li>
        <li>Atractiva para productos comerciales cerrados</li>
      </ul>
    </div>
  </div>
  <div class="callout"><strong>Dato curioso:</strong> la Switch usa parte del código de BSD, pero el kernel (Horizon) es propio de Nintendo.</div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Formas de interactuar</div>
  <h2 class="slide-title"><span>GUI</span> vs <span>CLI</span></h2>
  <div class="two-col">
    <div class="col-card">
      <h3>GUI</h3>
      <ul>
        <li>Interfaz gráfica de usuario</li>
        <li>Intuitiva, visual</li>
        <li>Automatización menos directa</li>
      </ul>
    </div>
    <div class="col-card">
      <h3>CLI</h3>
      <ul>
        <li>Interfaz de línea de comandos</li>
        <li>Uso de recursos reducido</li>
        <li>Fácil de automatizar con scripts</li>
      </ul>
    </div>
  </div>
</div>

---
layout: none
---

<div class="content-slide gaming-question-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Gaming en Linux</div>
  <h2 class="slide-title">¿Por qué <span>SteamOS</span> no es la solución al gaming en Linux?</h2>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">¿Es Wine un emulador?</div>
  <h2 class="slide-title"><span>Proton</span>: correr juegos de Windows en Linux</h2>
  <div class="topic-list">
    <div class="topic-item">Wine<span class="note">Capa de compatibilidad para programas de Windows</span></div>
    <div class="topic-item">Valve<span class="note">La empresa detrás de Steam y del impulso al gaming en Linux</span></div>
    <div class="topic-item">Proton<span class="note">Basado en Wine, con ajustes para juegos</span></div>
    <div class="topic-item">Darling<span class="note">Como Wine, pero para programas de macOS</span></div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">¿Cuál es el panorama?</div>
  <h2 class="slide-title">Drivers gráficos: <span>AMD, NVIDIA e Intel</span></h2>
  <div class="two-col">
    <div class="col-card">
      <h3>Drivers de código abierto</h3>
      <ul>
        <li>Mesa: implementaciones libres de OpenGL y Vulkan</li>
        <li>Nouveau: driver libre para tarjetas NVIDIA</li>
      </ul>
    </div>
    <div class="col-card">
      <h3>Fabricantes</h3>
      <ul>
        <li>AMD: buen soporte open source</li>
        <li>Intel: integrado, buen soporte open source</li>
        <li>NVIDIA: módulos abiertos y partes propietarias</li>
      </ul>
    </div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Preparando el entorno</div>
  <h2 class="slide-title">Virtualización: <span>nuestra herramienta de práctica</span></h2>
  <p class="slide-sub">Se permite usar cualquier máquina virtual durante el curso.</p>
  <div class="compare-grid compare-grid-three">
    <div class="compare-card highlight">
      <span class="tag">Opción recomendada</span>
      <h3>VMware Workstation</h3>
      <ul>
        <li>Hipervisor de tipo 2</li>
        <li>Gratuito</li>
        <li>Disponible en Windows y Linux</li>
      </ul>
    </div>
    <div class="compare-card">
      <span class="tag">Multiplataforma</span>
      <h3>VirtualBox</h3>
      <ul>
        <li>Hipervisor de tipo 2</li>
        <li>Gratuito y multiplataforma</li>
        <li>No es recomendable usarlo junto a Hyper-V</li>
      </ul>
    </div>
    <div class="compare-card">
      <span class="tag">En Windows</span>
      <h3>Hyper-V</h3>
      <ul>
        <li>Hipervisor de tipo 1</li>
        <li>Disponible en Windows Pro, Enterprise y Education</li>
        <li>Integrado en esas ediciones de Windows</li>
      </ul>
    </div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Confianza en lo que descargas</div>
  <h2 class="slide-title">Verificación de <span>integridad</span></h2>
  <p class="slide-sub">Antes de instalar, compara el hash del archivo con el publicado por la distribución.</p>
  <div class="win-window">
    <div class="win-header">
      <div class="win-title"><span class="win-icon"></span> Windows PowerShell</div>
      <div class="win-controls">
        <div class="win-btn">−</div>
        <div class="win-btn">▢</div>
        <div class="win-btn close">×</div>
      </div>
    </div>
    <div class="win-body">
      <div class="term-line"><span class="win-prompt">PS C:\Descargas&gt;</span> (Get-FileHash .\ubuntu.iso -Algorithm SHA256).Hash</div>
      <div class="term-line win-out">[64 caracteres hexadecimales]</div>
    </div>
  </div>
</div>

---
layout: none
---

<div class="content-slide">
  <div class="mini-corner"></div>
  <div class="mini-footer"></div>
  <div class="kicker">Primer comando</div>
  <h2 class="slide-title"><span>uname</span>: preguntándole al sistema quién es</h2>
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
      <div v-click="1">
        <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">uname</span> <span v-mark.circle.red="4">-a</span></div>
        <div class="term-line term-out">Linux dicachy 7.1.2-1-cachyos-bore #1 SMP PREEMPT_DYNAMIC x86_64 GNU/Linux</div>
      </div>
      <div v-click="2" style="margin-top:10px">
        <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">uname</span> <span v-mark.circle.red="5">-r</span></div>
        <div class="term-line term-out">7.1.2-1-cachyos-bore</div>
      </div>
      <div v-click="3" style="margin-top:10px">
        <div class="term-line"><span class="term-prompt">❯</span> <span class="term-cmd">uname</span> <span v-mark.circle.red="6">-m</span></div>
        <div class="term-line term-out">x86_64</div>
      </div>
    </div>
  </div>
  <div v-click="7" class="callout">Las opciones <code>-a</code>, <code>-r</code> y <code>-m</code> también se conocen como <em>flags</em>.</div>
</div>

---
layout: none
---

<div class="closing-slide">
  <div class="closing-title">¿<span>Preguntas</span>?</div>
  <div class="closing-sub">Rocket Tech Academy - Fundamentos de Linux</div>
</div>
