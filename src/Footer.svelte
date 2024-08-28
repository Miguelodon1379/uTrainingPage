<script>
  import { onMount } from 'svelte';

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

<footer aria-label="Site Footer" class="bg-[#3d3d3d] fixed bottom-0 left-0 right-0 z-50">
  <div class="mx-auto flex h-16 max-w-screen-xl items-center gap-4 px-4 sm:gap-6 sm:px-6 lg:gap-8 lg:px-8">
    <nav aria-label="Footer Nav" class="flex justify-between w-full sm:gap-4 lg:gap-8">
      <a
        href="#intro"
        on:click="{(e) => scrollToSection(e, 'intro')}"
        class="text-sm sm:text-base text-gray-400 hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'intro'}
        class:glow-white={activeSection === 'intro'}
      >
        Inicio
      </a>
      <a
        href="#vision-mission"
        on:click="{(e) => scrollToSection(e, 'vision-mission')}"
        class="text-sm sm:text-base text-gray-400 hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'vision-mission'}
        class:glow-white={activeSection === 'vision-mission'}
      >
        Misión y Visión
      </a>
      <a
        href="#excercise"
        on:click="{(e) => scrollToSection(e, 'excercise')}"
        class="text-sm sm:text-base text-gray-400 hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'excercise'}
        class:glow-white={activeSection === 'excercise'}
      >
        Tracks
      </a>
      <a
        href="#ai"
        on:click="{(e) => scrollToSection(e, 'ai')}"
        class="text-sm sm:text-base text-gray-400 hover:text-white transition duration-300 ease-in-out"
        class:text-white={activeSection === 'ai'}
        class:glow-white={activeSection === 'ai'}
      >
        Nuestra IA
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

  @media (max-width: 600px) {
    .text-sm {
      font-size: 0.875rem; /* Tamaño de letra más pequeño en dispositivos móviles */
    }

    footer {
      height: 56px; /* Altura reducida para móviles */
    }
  }
</style>
