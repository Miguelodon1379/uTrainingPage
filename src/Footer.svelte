<script>
  import { onMount } from 'svelte';
  import logo from './assets/logo.png'
  let activeSection = 'intro';

  function scrollToSection(event, sectionId) {
    event.preventDefault();
    const section = document.getElementById(sectionId);
    if (section) {
      section.scrollIntoView({ behavior: 'smooth' });
      activeSection = sectionId;
    }
  }

  onMount(() => {
    const sections = document.querySelectorAll('section');

    const observerOptions = {
      root: null,
      rootMargin: '0px',
      threshold: 0.5,
    };

    const observerCallback = (entries) => {
      entries.forEach(entry => {
        if (entry.isIntersecting) {
          if (entry.target.id === 'excercise' || entry.target.id === 'food') {
            activeSection = 'excercise';
          } else {
            activeSection = entry.target.id;
          }
        }
      });
    };

    const observer = new IntersectionObserver(observerCallback, observerOptions);

    sections.forEach(section => {
      observer.observe(section);
    });

    return () => {
      observer.disconnect();
    };
  });
</script>

<footer aria-label="Site Footer" class="bg-[#3d3d3d] fixed bottom-4 left-4 right-4 z-50 rounded-lg">
  <div class="mx-auto flex h-12 max-w-screen-sm items-center gap-2 px-4 sm:gap-4 sm:px-6 lg:gap-6 lg:px-8">
    <nav aria-label="Footer Nav" class="flex justify-between w-full sm:gap-2 lg:gap-4">
      <a
        href="#intro"
        on:click="{(e) => scrollToSection(e, 'intro')}"
        class="text-xs sm:text-sm text-[#dfe1c4] hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'intro'}
        class:glow-white={activeSection === 'intro'}
      >
        Inicio
      </a>
      <a
        href="#vision-mission"
        on:click="{(e) => scrollToSection(e, 'vision-mission')}"
        class="text-xs sm:text-sm text-[#dfe1c4] hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'vision-mission'}
        class:glow-white={activeSection === 'vision-mission'}
      >
        Misión y Visión
      </a>
      <a
        href="#excercise"
        on:click="{(e) => scrollToSection(e, 'excercise')}"
        class="text-xs sm:text-sm text-[#dfe1c4] hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'excercise'}
        class:glow-white={activeSection === 'excercise'}
      >
        Tracks
      </a>
      <a
        href="#ai"
        on:click="{(e) => scrollToSection(e, 'ai')}"
        class="text-xs sm:text-sm text-[#dfe1c4] hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'ai'}
        class:glow-white={activeSection === 'ai'}
      >
        Nuestra IA
      </a>
      <a
        href="#download"
        on:click="{(e) => scrollToSection(e, 'download')}"
        class="text-xs sm:text-sm text-[#dfe1c4] hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'download'}
        class:glow-white={activeSection === 'download'}
      >
        Descarga
      </a>
    </nav>
  </div>
</footer>

<style>
  .glow-white {
    text-shadow: 0 0 10px #fff;
    transform: scale(1.1);
    transition: transform 0.3s ease;
  }

  footer {
    padding: 6px 8px; /* Reduce el espacio interno para hacerlo más pequeño */
    height: 48px; /* Altura más pequeña para el footer */
  }

  .text-xs {
    font-size: 0.75rem; /* Tamaño de letra más pequeño */
    line-height: 1.5; /* Ajusta la altura de línea para centrar verticalmente */
  }

  .rounded-lg {
    border-radius: 12px; /* Bordes redondeados */
  }

  @media (max-width: 600px) {
    .text-xs {
      font-size: 0.8rem; /* Tamaño de letra más pequeño en dispositivos móviles */
      line-height: 1.4; /* Altura de línea ajustada en móviles */
    }

    footer {
      padding: 4px 6px; /* Espaciado reducido para móviles */
      height: 40px; /* Altura aún más pequeña en móviles */
    }
  }
</style>
