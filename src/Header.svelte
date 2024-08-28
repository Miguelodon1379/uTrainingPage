<script>
    import { onMount } from 'svelte';
    import logo from './assets/logo.png'
    import face from './assets/facebook.png'
    import insta from './assets/instagram.png'

    let activeSection = 'intro'; 

    function scrollToSection(event, sectionId) {
      event.preventDefault()
      const section = document.getElementById(sectionId)
      if (section) {
        section.scrollIntoView({ behavior: 'smooth' })
        activeSection = sectionId
      }
    }

  onMount(() => {
    const sections = document.querySelectorAll('section');

    const observerOptions = {
      root: null,
      rootMargin: '0px',
      threshold: 0.5, // Sección está activa cuando 50% es visible
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


<!-- Top bar -->
<div class="border-b border-slate-200 bg-[#fbfaef] z-40 fixed top-0 left-0 right-0">
  <div class="mx-auto grid w-full max-w-full grid-cols-4 gap-6 py-2 px-6 text-sm text-slate-500 md:grid-cols-8 lg:max-w-5xl lg:grid-cols-12 xl:max-w-7xl 2xl:max-w-[96rem]">
    <div class="items-center justify-end col-span-2 gap-6 md:col-span-4 lg:col-span-6">
      <div class="flex items-center justify-end gap-4">
        <!-- Facebook Icon -->
        <a href="https://www.facebook.com" target="_blank" class="transition-colors duration-300 hover:text-[#4d6344] text-[#000000]">
          <svg xmlns="http://www.w3.org/2000/svg" fill="none" viewBox="0 0 48 48" height="16" width="16" role="graphics-symbol" aria-labelledby="title-tb01 desc-tb01">
            <title id="title-tb01">Facebook Icon</title>
            <desc id="desc-tb01">Facebook logo</desc>
            <path fill="currentColor" {...{"fillRule": "evenodd"}} d="M47.5 24C47.5 11.288 36.712 0.5 24 0.5S0.5 11.288 0.5 24C0.5 35.449 9.074 44.699 20.062 47.07V30.546H14.672v-6.545h5.39v-4.833c0-5.504 3.288-8.54 8.312-8.54 2.409 0 4.925.43 4.925.43v5.41h-2.774c-2.734 0-3.584 1.697-3.584 3.444v4.088h6.094l-.974 6.546h-5.12v16.524C38.926 44.7 47.5 35.448 47.5 24Z" clipRule="evenodd" />
          </svg>
        </a>

        <!-- Instagram Icon -->
        <a href="https://www.instagram.com" target="_blank" class="transition-colors duration-300 hover:text-[#4d6344] text-[#000000]">
          <svg xmlns="http://www.w3.org/2000/svg" viewBox="0 0 24 24" fill="currentColor" width="20" height="20" aria-labelledby="instagramIconTitle" role="img">
            <title id="instagramIconTitle">Instagram Icon</title>
            <path d="M12,2.163c3.2,0,3.584,0.012,4.849,0.07c1.17,0.054,1.97,0.236,2.615,0.503c0.676,0.279,1.25,0.65,1.812,1.212s0.934,1.136,1.212,1.812c0.267,0.645,0.449,1.445,0.503,2.615c0.058,1.265,0.07,1.649,0.07,4.849s-0.012,3.584-0.07,4.849c-0.054,1.17-0.236,1.97-0.503,2.615c-0.279,0.676-0.65,1.25-1.212,1.812s-1.136,0.934-1.812,1.212c-0.645,0.267-1.445,0.449-2.615,0.503c-1.265,0.058-1.649,0.07-4.849,0.07s-3.584-0.012-4.849-0.07c-1.17-0.054-1.97-0.236-2.615-0.503c-0.676-0.279-1.25-0.65-1.812-1.212s-0.934-1.136-1.212-1.812c-0.267-0.645-0.449-1.445-0.503-2.615c-0.058-1.265-0.07-1.649-0.07-4.849s0.012-3.584,0.07-4.849c0.054-1.17,0.236-1.97,0.503-2.615c0.279-0.676,0.65-1.25,1.212-1.812s1.136-0.934,1.812-1.212c0.645-0.267,1.445-0.449,2.615-0.503C8.416,2.175,8.8,2.163,12,2.163 M12,0C8.735,0,8.332,0.014,7.053,0.073c-1.281,0.059-2.156,0.258-2.909,0.553C3.063,0.926,2.353,1.358,1.646,2.065S0.926,3.063,0.626,3.944c-0.295,0.753-0.494,1.628-0.553,2.909C0.014,8.332,0,8.735,0,12c0,3.265,0.014,3.668,0.073,4.947c0.059,1.281,0.258,2.156,0.553,2.909c0.3,0.881,0.732,1.591,1.439,2.298c0.707,0.707,1.417,1.139,2.298,1.439c0.753,0.295,1.628,0.494,2.909,0.553C8.332,23.986,8.735,24,12,24s3.668-0.014,4.947-0.073c1.281-0.059,2.156-0.258,2.909-0.553c0.881-0.3,1.591-0.732,2.298-1.439c0.707-0.707,1.139-1.417,1.439-2.298c0.295-0.753,0.494-1.628,0.553-2.909C23.986,15.668,24,15.265,24,12s-0.014-3.668-0.073-4.947c-0.059-1.281-0.258-2.156-0.553-2.909c-0.3-0.881-0.732-1.591-1.439-2.298c-0.707-0.707-1.417-1.139-2.298-1.439c-0.753-0.295-1.628-0.494-2.909-0.553C15.668,0.014,15.265,0,12,0L12,0z M12,5.838c-3.403,0-6.162,2.758-6.162,6.162c0,3.403,2.758,6.162,6.162,6.162c3.403,0,6.162-2.758,6.162-6.162C18.162,8.596,15.403,5.838,12,5.838L12,5.838z M12,16.338c-2.391,0-4.338-1.946-4.338-4.338c0-2.391,1.946-4.338,4.338-4.338c2.391,0,4.338,1.946,4.338,4.338C16.338,14.391,14.391,16.338,12,16.338L12,16.338z M18.406,4.594c-0.796,0-1.441,0.646-1.441,1.441c0,0.796,0.646,1.441,1.441,1.441c0.796,0,1.441-0.646,1.441-1.441C19.847,5.239,19.202,4.594,18.406,4.594L18.406,4.594z" />
          </svg>
        </a>
        

      </div>
    </div>
  </div>
</div>
  
<!-- Main header -->
<header aria-label="Site Header" class="bg-[#3d3d3d] fixed top-8 left-0 right-0 z-50">
  <div class="mx-auto flex h-16 max-w-screen-xl items-center gap-8 px-4 sm:px-6 lg:px-8">
    <a class="block text-teal-600" href="/">
      <span class="sr-only">Home</span>
      <img src={logo} alt="Home" class="h-12 w-auto"/>
    </a>
    <div class="flex flex-1 items-center justify-between">
      <nav aria-label="Site Nav" class="hidden md:flex md:gap-4 lg:gap-8">
        <a
          href="#intro"
          on:click="{(e) => scrollToSection(e, 'intro')}"
          class:text-white={activeSection === 'intro'}
          class:glow-white={activeSection === 'intro'}
        >
          Inicio
        </a>
        <a
          href="#vision-mission"
          on:click="{(e) => scrollToSection(e, 'vision-mission')}"
          class:text-white={activeSection === 'vision-mission'}
          class:glow-white={activeSection === 'vision-mission'}
        >
          Misión y Visión
        </a>
        <a
          href="#excercise"
          on:click="{(e) => scrollToSection(e, 'excercise')}"
          class:text-white={activeSection === 'excercise'}
          class:glow-white={activeSection === 'excercise'}
        >
          Tracks
        </a>
        <a
          href="#ai"
          on:click="{(e) => scrollToSection(e, 'ai')}"
          class:text-white={activeSection === 'ai'}
          class:glow-white={activeSection === 'ai'}
        >
          Nuestra IA
        </a>
        <a
          href="#download"
          on:click="{(e) => scrollToSection(e, 'download')}"
          class:text-white={activeSection === 'download'}
          class:glow-white={activeSection === 'download'}
        >
          Cómo descargarla
        </a>
      </nav>
      <div class="flex items-center gap-4">
        <a href="#" class="inline-flex h-12 min-w-36 items-center justify-start gap-2 whitespace-nowrap rounded border border-slate-50 bg-transparent px-2.5 text-sm font-semibold tracking-wide text-slate-50 transition duration-300 hover:border-[#dfe1c4] hover:text-[#dfe1c4] hover:[&_*]:fill-[#dfe1c4] focus:border-[#dfe1c4] focus:text-[#dfe1c4] focus:[&_*]:fill-[#dfe1c4] focus-visible:outline-none">
          <svg width="32" height="32" class="w-8 h-8" viewBox="0 0 40 40" fill="none" xmlns="http://www.w3.org/2000/svg" role="graphics-symbol" aria-label="Google play icon">
            <path d="M21.9219 19.6222L27.8405 13.7036L8.72367 2.95928C7.45668 2.27475 6.26976 2.17868 5.22895 2.92726L21.9219 19.6222ZM28.8316 26.5339L34.9843 23.0732C36.1853 22.4007 36.8438 21.4479 36.8438 20.3911C36.8438 19.3363 36.203 18.3993 35.0041 17.7267L29.4337 14.5983L23.1452 20.8495L28.8316 26.5339ZM4.20016 4.38239C4.07206 4.7767 4 5.21704 4 5.69941V35.1322C4 35.8948 4.16813 36.5513 4.47237 37.0738L20.6789 20.8652L4.20016 4.38239ZM21.9219 22.1061L5.8054 38.2246C6.11364 38.3427 6.4459 38.4048 6.79617 38.4048C7.42065 38.4048 8.07116 38.2206 8.73367 37.8524L27.258 27.4503L21.9219 22.1061Z" fill="currentColor"></path>
          </svg>
          <span class="flex flex-col">
            <span class="text-[10px] font-normal">Get it on</span>
            <span class="text-sm">Google Play</span>
          </span>
        </a>
      </div>
    </div>
  </div>
</header>

<style>
    .header-button {
    font-weight: 500;
    color: #333;
    background: none;
    border: none;
    cursor: pointer;
    transition: color 0.3s;
    text-decoration: none;
    }
    .header-button:hover {
    color: #000;
    }
    .text-gray-700 { color: #dfe1c4; }
    .bg-gray-100 { background-color: #f3f4f6; }
    
   header nav a {
    color: #dfe1c4;
    transition: color 0.3s ease;
  }

  header nav a:hover {
    color: white;
  }

  header nav a.text-white {
    color: white;
  }

  .glow-white {
    text-shadow: 0 0 10px #fff;
  }
</style>