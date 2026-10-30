<script setup>
import { ref } from 'vue'

const likes = ref(0)
const dislikes = ref(0)
const reaction = ref(null)

function react(type) {
  reaction.value = type
  type === 'like' ? likes.value++ : dislikes.value++
}
</script>

<template>
  <div class="page-shell">
    <header class="topbar">
      <a class="brand" href="#" aria-label="Inicio">
        <span class="brand-mark">H</span>
        <span>Hoja de vida</span>
      </a>
      <span class="availability"><span></span> Disponible para oportunidades</span>
    </header>

    <main class="resume">
      <section class="hero" aria-labelledby="person-name">
        <div class="hero-copy">
          <p class="eyebrow">PERFIL PROFESIONAL</p>
          <h1 id="person-name">Álvaro Ramírez<br /><span>González</span></h1>
          <p class="role">Desarrollador frontend y backend</p>
          <p class="intro">
            Desarrollo aplicaciones y soluciones web. Tengo experiencia trabajando en frontend y
            backend, y creando aplicaciones sencillas para Android.
          </p>
          <a class="contact-link" href="mailto:alvarodavidgonzalez@gmail.com">
            Hablemos <span aria-hidden="true">↗</span>
          </a>
        </div>
        <div class="portrait" aria-label="Avatar de Álvaro Ramírez González">
          <div class="portrait-halo"></div>
          <div class="portrait-card">
            <span>AG</span>
            <small>DESARROLLO<br />DE SOFTWARE</small>
          </div>
          <span class="portrait-caption">Frontend · Backend · Android</span>
        </div>
      </section>

      <div class="section-rule">
        <span>01</span>
        <span>IDENTIDAD</span>
        <span class="rule-line"></span>
      </div>

      <section class="identity section-grid" aria-labelledby="identity-title">
        <div>
          <p class="eyebrow">UN POCO SOBRE MÍ</p>
          <h2 id="identity-title">Datos personales</h2>
        </div>
        <dl class="details-grid">
          <div><dt>Nombre completo</dt><dd>Álvaro Ramírez González</dd></div>
          <div><dt>Correo de contacto</dt><dd><a href="mailto:alvarodavidgonzalez@gmail.com">alvarodavidgonzalez@gmail.com</a></dd></div>
          <div><dt>Teléfono</dt><dd><a href="tel:+573243025424">324 302 5424</a></dd></div>
        </dl>
      </section>

      <div class="section-rule">
        <span>02</span>
        <span>FORMACIÓN</span>
        <span class="rule-line"></span>
      </div>

      <section class="section-grid" aria-labelledby="education-title">
        <div>
          <p class="eyebrow">TECNOLOGÍAS Y HERRAMIENTAS</p>
          <h2 id="education-title">Formación y<br />conocimientos</h2>
        </div>
        <div class="timeline">
          <article class="timeline-item">
            <span class="timeline-date">FRONTEND</span>
            <div>
              <h3>Desarrollo de interfaces web</h3>
              <p class="institution">Frameworks: Angular y React</p>
              <p>Creación de interfaces y aplicaciones web utilizando HTML y tecnologías frontend.</p>
            </div>
          </article>
          <article class="timeline-item">
            <span class="timeline-date">BACKEND</span>
            <div>
              <h3>Lenguajes y bases de datos</h3>
              <p class="institution">Java, PHP, Python y MySQL</p>
              <p>Conocimientos para desarrollar la lógica de aplicaciones y trabajar con bases de datos.</p>
            </div>
          </article>
          <article class="timeline-item">
            <span class="timeline-date">ANDROID</span>
            <div>
              <h3>Aplicaciones móviles sencillas</h3>
              <p class="institution">Android Studio y Kotlin</p>
              <p>Desarrollo de aplicaciones básicas para dispositivos Android.</p>
            </div>
          </article>
        </div>
      </section>

      <div class="section-rule">
        <span>03</span>
        <span>TRAYECTORIA</span>
        <span class="rule-line"></span>
      </div>

      <section class="section-grid experience" aria-labelledby="experience-title">
        <div>
          <p class="eyebrow">LO QUE HE HECHO</p>
          <h2 id="experience-title">Experiencia<br />laboral</h2>
        </div>
        <div class="timeline">
          <article class="timeline-item">
            <span class="timeline-date">DESARROLLO</span>
            <div>
              <h3>Desarrollador frontend y backend</h3>
              <p class="institution">Desarrollo de aplicaciones web</p>
              <p>Experiencia en desarrollo frontend y backend, trabajando con frameworks, lenguajes de programación y bases de datos.</p>
              <div class="tags"><span>Angular</span><span>React</span><span>Java</span><span>PHP</span><span>Python</span><span>MySQL</span></div>
            </div>
          </article>
          <article class="timeline-item">
            <span class="timeline-date">APLICACIONES</span>
            <div>
              <h3>Desarrollo para Android</h3>
              <p class="institution">Proyectos de aplicaciones sencillas</p>
              <p>Creación de aplicaciones móviles básicas usando Android Studio y Kotlin.</p>
              <div class="tags"><span>Android Studio</span><span>Kotlin</span><span>HTML</span></div>
            </div>
          </article>
        </div>
      </section>

      <section class="reaction-card" aria-label="Valora esta hoja de vida">
        <div>
          <p class="eyebrow">¿TE GUSTÓ MI PERFIL?</p>
          <h2>Tu opinión<br />también cuenta.</h2>
        </div>
        <div class="reaction-actions">
          <button
            class="reaction-button"
            :class="{ selected: reaction === 'like' }"
            type="button"
            :aria-pressed="reaction === 'like'"
            aria-label="Me gusta"
            @click="react('like')"
          >
            <span aria-hidden="true">👍</span><span>{{ likes }}</span>
          </button>
          <button
            class="reaction-button"
            :class="{ selected: reaction === 'dislike' }"
            type="button"
            :aria-pressed="reaction === 'dislike'"
            aria-label="No me gusta"
            @click="react('dislike')"
          >
            <span aria-hidden="true">👎</span><span>{{ dislikes }}</span>
          </button>
          <p class="reaction-hint" aria-live="polite">
            {{ reaction ? '¡Gracias por compartir tu opinión!' : 'Selecciona una reacción' }}
          </p>
        </div>
      </section>
    </main>

    <footer class="statusbar">
      <span class="status-dot"></span>
      <span>© 2026 Álvaro Ramírez González</span>
      <span class="footer-divider">/</span>
      <a href="https://www.behance.net/" target="_blank" rel="noopener noreferrer">
        Visita mi sitio personal <span aria-hidden="true">↗</span>
      </a>
      <span class="footer-note">Diseñado con intención.</span>
    </footer>
  </div>
</template>
